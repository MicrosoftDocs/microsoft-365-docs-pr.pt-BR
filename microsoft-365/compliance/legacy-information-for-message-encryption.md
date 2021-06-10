---
title: Informações herdadas de Criptografia de Mensagens do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Entenda como fazer a transição de arquivos herdados para Criptografia de Mensagens do Office 365 (OME) para sua organização.
ms.openlocfilehash: eabf655b6fa92a6f502ebe1e071d41f394f78929
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051823"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Informações herdadas de Criptografia de Mensagens do Office 365

Se você ainda não moveu sua organização para os novos recursos OME, mas já implantou o OME, as informações neste artigo se aplicarão à sua organização. A Microsoft recomenda que você faça um plano para mover para os novos recursos OME assim que for razoável para sua organização. Para obter instruções, [consulte Set up new Criptografia de Mensagens do Office 365 capabilities built on on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Se você quiser saber mais sobre como os novos recursos funcionam primeiro, [consulte Criptografia de Mensagens do Office 365](ome.md). O restante deste artigo refere-se ao comportamento OME antes da versão dos novos recursos OME.
  
Com o Criptografia de Mensagens do Office 365, sua empresa pode enviar e receber mensagens criptografadas entre pessoas de dentro e de fora da sua organização. Criptografia de Mensagens do Office 365 funciona com Outlook.com, Yahoo, Gmail e outros serviços de email. A criptografia de mensagem de email ajuda a garantir que somente os destinatários pretendido possam exibir o conteúdo da mensagem.
  
Aqui estão alguns exemplos:
  
- Um funcionário do banco envia extratos de cartão de crédito aos clientes

- Um representante da empresa de seguros fornece detalhes da política aos clientes

- Um agente hipotecária solicita informações financeiras de um cliente para um aplicativo de empréstimo

- Um provedor de saúde envia informações de assistência à saúde para os pacientes

- Um advogado envia informações confidenciais para um cliente ou outro advogado

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Como Criptografia de Mensagens do Office 365 funciona sem os novos recursos

Criptografia de Mensagens do Office 365 é um serviço online criado com base Microsoft Azure Gerenciamento de Direitos (Azure RMS). Com o Azure RMS, os administradores podem definir regras de fluxo de emails para determinar as condições de criptografia. Por exemplo, uma regra pode exigir a criptografia de todas as mensagens endereçadas a um destinatário específico.
  
Quando alguém envia uma mensagem de email Exchange Online que corresponde a uma regra de criptografia, a mensagem é enviada com um anexo HTML. O destinatário abre o anexo HTML e segue instruções para exibir a mensagem criptografada no Criptografia de Mensagens do Office 365 portal. O destinatário pode optar por exibir a mensagem ao entrar com uma conta da Microsoft ou uma empresa ou escola associada ao Office 365, ou usando um código de passagem única. Ambas as opções ajudam a garantir que somente o destinatário pretendido pode exibir a mensagem criptografada. Esse processo é muito diferente para os novos recursos OME.
  
O diagrama a seguir resume a passagem de uma mensagem de email pelo processo de criptografia e de descriptografia.
  
![Diagrama mostrando o caminho de um email criptografado](../media/O365-Office365MessageEncryption-Concept.png)
  
Para obter mais informações, consulte Informações de serviço para Criptografia de Mensagens do Office 365 anteriores à [versão dos novos recursos OME.](legacy-information-for-message-encryption.md#LegacyServiceInfo)
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definindo regras de fluxo de email para Criptografia de Mensagens do Office 365 que não usam os novos recursos OME

Para habilitar Criptografia de Mensagens do Office 365 sem os novos recursos, os administradores Exchange Online e Proteção do Exchange Online definem Exchange de fluxo de emails. Essas regras determinam em que condições as mensagens de email devem ser criptografadas, bem como as condições para remover a criptografia de mensagens. Quando uma ação de criptografia é definida para uma regra, o serviço executa a ação em todas as mensagens que corresponderem às condições de regra antes de enviar as mensagens.

As regras de fluxo de emails são flexíveis, o que permite combinar condições para que você possa atender a requisitos de segurança específicos em uma única regra. Por exemplo, você pode criar uma regra para criptografar todas as mensagens que contenham palavras-chave específicas e que sejam endereçadas a destinatários externos. A Criptografia de Mensagens do Office 365 também criptografa os emails de respostas dos destinatários e é possível criar uma regra para descriptografar essas respostas para a comodidade dos seus usuários de email. Dessa forma, os usuários em sua organização não terão que entrar no portal de criptografia para exibir respostas.
  
Para obter mais informações sobre como criar Exchange de fluxo de emails, consulte [Define Rules for Criptografia de Mensagens do Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Use o EAC para criar uma regra de fluxo de emails para criptografar mensagens de email sem os novos recursos OME

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre [no](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365 .

2. Escolha o **painel** Administrador.

3. No centro Microsoft 365 de administração, escolha **Centros de administração** \> **Exchange**.

4. No EAC, vá para **Regras de fluxo de email** e selecione \>  **Novo** ícone Criar ![ uma nova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regra.** Para obter mais informações sobre como usar o EAC, [consulte Exchange centro de administração em Exchange Online](/exchange/exchange-admin-center).

5. Em **Nome**, digite um nome para a regra, como Criptografar email para DrToniRamos@hotmail.com.

6. Em **Aplicar esta regra se**, selecione uma condição e digite um valor, se necessário. Por exemplo, para criptografar mensagens enviadas a DrToniRamos@hotmail.com:

   1. Em **Aplicar esta regra se**, selecione **o destinatário é**.

   2. Escolha um nome existente na lista de contatos ou digite um novo endereço de email na caixa **verificar nomes**.

      - Para selecionar um nome existente, escolha-o na lista e clique em **OK**.

      - Para inserir um novo nome, digite um endereço de email na **caixa** de nomes de seleção e selecione nomes **de verificação** \> **OK**.

7. Para adicionar mais condições, escolha **Mais opções** e selecione **adicionar condição** e selecione na lista.

   Por exemplo, para aplicar a regra somente se o destinatário estiver fora da sua organização, selecione **adicionar** condição e selecione O destinatário é **externo/interno** Fora \> **da organização** \> **OK**.

8. Para habilitar a criptografia sem usar os novos  recursos OME, em **Fazer** o seguinte, selecione Modificar a segurança da mensagem Aplicar a versão anterior do \> **OME** e escolha **Salvar**.

   Se você receber um erro de que o licenciamento do IRM não está habilitado, então não está usando o OME herdado.

9. (Opcional) Escolha **adicionar ação** para especificar outra ação.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Use Exchange Online PowerShell para criar uma regra de fluxo de emails para criptografar mensagens de email sem os novos recursos OME

1. Conecte-se ao PowerShell do Exchange Online. Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](/powershell/exchange/connect-to-exchange-online-powershell).

2. Criar uma regra usando o cmdlet **New-TransportRule** e definir o _parâmetro ApplyOME_ como `$true` .

   Este exemplo exige que todas as mensagens de email enviadas DrToniRamos@hotmail.com sejam criptografadas.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   Onde

   - O nome exclusivo da nova regra é "Criptografar regra para o Dr. Toni Ramos".
   - O _parâmetro SentTo_ especifica os destinatários da mensagem (identificados pelo nome, endereço de email, nome diferenciado, etc.). Neste exemplo, o destinatário é identificado pelo endereço de email "DrToniRamos@hotmail.com".
   - O _parâmetro SentToScope_ especifica o local dos destinatários da mensagem. Neste exemplo, a caixa de correio do destinatário está no hotmail e não faz parte da organização, portanto, o valor `NotInOrganization` é usado.

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Remover criptografia de respostas de email criptografadas sem os novos recursos OME

Quando os usuários de email enviam mensagens criptografadas, os destinatários dessas mensagens podem responder com respostas criptografadas. Você pode criar regras de fluxo de emails para remover automaticamente a criptografia das respostas para que os usuários de email em sua organização não tenham que entrar no portal de criptografia para exibi-los. Você pode usar os cmdlets EAC ou Windows PowerShell para definir essas regras. Você pode descriptografar mensagens enviadas de dentro da sua organização ou mensagens que são respostas a mensagens enviadas de dentro de sua organização. Não é possível descriptografar mensagens criptografadas provenientes de fora da sua organização.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Use o EAC para criar uma regra para remover a criptografia de respostas de email criptografadas sem os novos recursos OME

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador, entre [Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o **painel** Administrador.

3. No centro Microsoft 365 de administração, escolha **Centros de administração** \> **Exchange**.

4. No EAC, vá para **Regras de fluxo de email** e selecione \>  **Novo** ícone Criar ![ uma nova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regra.** Para obter mais informações sobre como usar o EAC, [consulte Exchange centro de administração em Exchange Online](/exchange/exchange-admin-center).

5. Em **Nome**, digite um nome para a regra, como Remover criptografia do email de entrada.

6. In **Apply this rule if select** the conditions where encryption should be removed from messages, such as The recipient is **located** Inside \> **the organization**.

7. Em **Fazer o seguinte**, selecione Modificar a segurança da **mensagem** Remover a versão anterior \> **do OME**.

8. Selecione **Salvar**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Use Exchange Online PowerShell para criar uma regra para remover a criptografia de respostas de email criptografadas sem os novos recursos OME

1. Conecte-se ao PowerShell do Exchange Online. Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](/powershell/exchange/connect-to-exchange-online-powershell).

2. Criar uma regra usando o cmdlet **New-TransportRule** e definir o _parâmetro RemoveOME_ como `$true` .

   Este exemplo remove a criptografia de todos os emails enviados aos destinatários na organização.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   Onde

   - O nome exclusivo da nova regra é "Remover criptografia do email de entrada".
   - O _parâmetro SentToScope_ especifica o local dos destinatários da mensagem. Neste exemplo, o valor `InOrganization` é usado, o que indica um dos seguintes:
     - O destinatário é uma caixa de correio, usuário de email, grupo ou pasta pública habilitada para email em sua organização.
     - O endereço de email do destinatário está em um domínio aceito configurado como um domínio autoritativo ou um domínio de retransmissão interno em sua _organização,_ e a mensagem foi enviada ou recebida por meio de uma conexão autenticada.

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/New-TransportRule).

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>Envio, exibição e resposta a mensagens criptografadas sem os novos recursos

Com Criptografia de Mensagens do Office 365, as mensagens de email são criptografadas automaticamente, com base em regras definidas pelo administrador. Um email com uma mensagem criptografada chega à Caixa de Entrada do destinatário com um arquivo HTML anexado.
  
Os destinatários seguem instruções na mensagem para abrir o anexo e autenticar usando uma conta da Microsoft ou uma empresa ou escola associada ao Office 365. Se os destinatários não têm nenhuma conta, eles são direcionados para criar uma conta da Microsoft que permitirá que eles entrem para exibir a mensagem criptografada. Como alternativa, os destinatários podem optar por obter um código de passagem única para exibir a mensagem. Depois de entrar ou usar um código de passagem única, os destinatários podem exibir a mensagem descriptografada e enviar uma resposta criptografada.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalizar mensagens criptografadas com Criptografia de Mensagens do Office 365

Como administrador Exchange Online e Proteção do Exchange Online, você pode personalizar suas mensagens criptografadas. Por exemplo, você pode adicionar a marca e o logotipo da sua empresa, especificar uma introdução e adicionar texto de aviso de isenção de responsabilidade em mensagens criptografadas e no portal onde os destinatários visualizam suas mensagens criptografadas. Usando cmdlets do Windows PowerShell, você pode personalizar os seguintes aspectos da experiência de visualização dos destinatários de mensagens de email criptografadas.

- Texto introdutório do email que contém a mensagem criptografada

- Texto do aviso de isenção de responsabilidade do email que contém a mensagem criptografada

- Texto do portal que aparecerá no portal de visualização da mensagem

- Logotipo que será exibido na mensagem de email e no portal de visualização

Você também pode reverter para a aparência padrão a qualquer momento.
  
O exemplo a seguir mostra um logotipo personalizado para a ContosoPharma no anexo de email:

> [!div class="mx-imgBorder"]
> ![Exemplo da página de exibição de mensagem criptografada](../media/TA-OME-3attachment2.jpg)
  
**Para personalizar mensagens de email de criptografia e o portal de criptografia com a marca da sua organização**
  
1. Conexão usar Exchange Online PowerShell Remoto, conforme descrito em [Conexão para Exchange Online Usando o PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Use o cmdlet Set-OMEConfiguration conforme descrito aqui: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) ou use a tabela a seguir para obter orientações.

   **Opções de personalização de criptografia**

   | Para personalizar este recurso da experiência com criptografia | Utilize estes comandos do Windows PowerShell |
   |:-----|:-----|
   |Texto padrão que acompanha as mensagens de email criptografadas  <br/> O texto padrão é exibido acima das instruções para a exibição de mensagens criptografadas  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
   |Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
   |Texto que aparece na parte superior do portal de exibição do email criptografado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
   |Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de arquivo com suporte: .png, .jpg, .bmp ou .tiff  <br/> Tamanho ideal do arquivo de logotipo: menos que 40 KB  <br/> Tamanho ideal da imagem de logotipo: 170 pixels x 70 pixels  <br/> |

**Para remover personalizações de marca de mensagens de email de criptografia e o portal de criptografia**
  
1. Conexão usar Exchange Online PowerShell Remoto, conforme descrito em [Conexão para Exchange Online Usando o PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Use o cmdlet Set-OMEConfiguration conforme descrito aqui: [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration). Para remover as personalizações de marca da sua organização dos valores DisclaimerText, EmailText e PortalText, de definir o valor como uma cadeia de caracteres vazia,  `""` . Para todos os valores de imagem, como Logo, de definir o valor como  `"$null"` .

   **Opções de personalização de criptografia**

   | Para reverter esse recurso da experiência de criptografia para o texto e a imagem padrões | Utilize estes comandos do Windows PowerShell |
   |:-----|:-----|
   |Texto padrão que acompanha as mensagens de email criptografadas  <br/> O texto padrão é exibido acima das instruções para a exibição de mensagens criptografadas  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
   |Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
   |Texto que aparece na parte superior do portal de exibição do email criptografado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Exemplo revertendo de volta para o padrão:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
   |Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Exemplo revertendo de volta para o padrão:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Informações de serviço para Criptografia de Mensagens do Office 365 anteriores à versão dos novos recursos OME
<a name="LegacyServiceInfo"> </a>

A tabela a seguir fornece detalhes técnicos para o serviço Criptografia de Mensagens do Office 365 antes da versão dos novos recursos OME.
  
| Detalhes do serviço | Descrição |
|:-----|:-----|
|Requisitos do dispositivo cliente  <br/> |As mensagens criptografadas podem ser visualizadas em qualquer dispositivo cliente, desde que o anexo HTML possa ser aberto em um navegador moderno compatível com Postagem de Formulário.  <br/> |
|Conformidade com algoritmos de criptografia e Normas Federais de Processamento de Informações (FIPS)  <br/> |A Criptografia de Mensagens do Office 365 usa as mesmas chaves de criptografia do Windows Information Rights Management (IRM) e dá suporte ao Modo Criptográfico 2 (chave 2K para RSA e chave de 256 bits para sistemas SHA-1). Para obter mais informações sobre os modos criptográficos de IRM subjacentes, consulte [AD RMS Cryptographic Modes](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).  <br/> |
|Tipos de mensagem suportados  <br/> |A Criptografia de Mensagens do Office 365 é suportada apenas para itens que possuem uma identificação de classe de mensagem de **IPM.Note**. Para obter mais informações, consulte [Tipos de item e classes de mensagem](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes).  <br/> |
|Limites de tamanhos de mensagens  <br/> |A Criptografia de Mensagens do Office 365 pode criptografar mensagens de até 25 megabytes. Para obter mais detalhes sobre os limites de tamanho da mensagem, [consulte Exchange Online Limites](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).  <br/> |
|Exchange Online de retenção de email  <br/> |Exchange Online não armazena as mensagens criptografadas.  <br/> |
|Suporte de idioma para a Criptografia de Mensagens do Office 365  <br/> | Office 365 A criptografia de mensagens Microsoft 365 idiomas, da seguinte forma:  <br/>  As mensagens de email de entrada e os arquivos HTML anexados são localizados com base nas configurações de idioma do remetente.  <br/>  O portal de visualização está localizado com base nas configurações do navegador do destinatário.  <br/>  O corpo (conteúdo) da mensagem criptografada não está localizado.  <br/> |
|Informações de privacidade para o Portal OME e o aplicativo do Visualizador OME  <br/> |A [Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) fornece informações detalhadas sobre o que a Microsoft faz e não faz com suas informações particulares.  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>Perguntas frequentes sobre o OME herdado
<a name="LegacyServiceInfo"> </a>

Tem perguntas sobre Criptografia de Mensagens do Office 365? Veja algumas respostas. Se você não conseguir encontrar o que precisa, verifique os fóruns do [Microsoft Tech Community para Office 365](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365).
  
 **P. Meus usuários enviam mensagens de email criptografadas para destinatários fora de nossa organização. Há algo que os destinatários externos tenham que fazer para ler e responder a mensagens de email criptografadas com Criptografia de Mensagens do Office 365?**
  
Destinatários fora da sua organização que recebem Microsoft 365 mensagens criptografadas podem exibi-los de duas maneiras:
  
- Ao entrar com uma conta da Microsoft ou uma conta de trabalho ou de estudante associada ao Office 365.

- Usando um código de passagem única.

 **P. As Microsoft 365 criptografadas são armazenadas na nuvem ou nos servidores Microsoft?**
  
Não, as mensagens criptografadas são mantidas no sistema de email do destinatário e, quando o destinatário abre a mensagem, ela é postada temporariamente para exibição nos servidores Microsoft. As mensagens não são armazenadas lá.
  
 **P. Posso personalizar mensagens de email criptografadas com minha marca?**
  
Sim. É possível usar os cmdlets do Windows PowerShell para personalizar o texto padrão exibido na parte superior da mensagem de email criptografada, o texto do aviso de isenção de responsabilidade e o logotipo que você deseja usar nas mensagens de email e no portal de criptografia. Esse recurso agora está disponível no OMEv2. Para obter detalhes, consulte [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **P. O serviço exige uma licença para cada usuário da organização?**
  
A licença é obrigatória para os usuários da organização que enviam emails criptografados.
  
 **P. São exigidas assinaturas para os destinatários externos?**
  
Não, os destinatários externos não necessitam de uma assinatura para ler ou responder mensagens criptografadas.
  
 **P. Como é Criptografia de Mensagens do Office 365 diferente dos Serviços de Gerenciamento de Direitos (RMS)?**
  
O RMS fornece recursos de Proteção de Direitos de Informação para emails internos de uma organização, fornecendo modelos internos, como: Não encaminhar e Confidencial da Empresa. A Criptografia de Mensagens do Office 365 é compatível com a criptografia de mensagens de email para mensagens enviadas a destinatários externos e internos.
  
 **P. Como é Criptografia de Mensagens do Office 365 diferente de S/MIME?**
  
Basicamente, o S/MIME é uma tecnologia de criptografia do lado do cliente e exige uma infraestrutura de publicação e de gerenciamento de certificados complicada. Criptografia de Mensagens do Office 365 usa regras de fluxo de emails (também conhecidas como regras de transporte) e não depende da publicação de certificados.
  
 **P. Posso ler as mensagens criptografadas em dispositivos móveis?**
  
Sim, você pode exibir mensagens no Android e no iOS baixando os aplicativos do Visualizador OME na Google Play Store e na Loja do Apple App. Abra o anexo em HTML no aplicativo Visualizador do OME e, em seguida, siga as instruções para abrir sua mensagem criptografada. Para outros dispositivos móveis, você poderá abrir o anexo em HTML se o cliente de email for compatível com a Postagem de Formulário.
  
 **P. As respostas e as mensagens encaminhadas são criptografadas?**
  
Sim. As respostas continuam a ser criptografadas durante todo o decurso do thread.
  
 **P. O Criptografia de Mensagens do Office 365 fornece localização?**
  
O conteúdo HTML e de emails de entrada é localizado com base nas configurações de email do remetente. O portal de exibição é localizado com base nas configurações do navegador do destinatário. No entanto, o próprio corpo (conteúdo) da mensagem criptografada não é localizado.
  
 **P. Qual método de criptografia é usado para Criptografia de Mensagens do Office 365?**
  
Criptografia de Mensagens do Office 365 usa os Serviços de Gerenciamento de Direitos (RMS) como sua infraestrutura de criptografia. O método de criptografia usado depende do local que você obtém as chaves do RMS usadas para criptografar e descriptografar mensagens.
  
- Se você usar Microsoft Azure RMS para obter as chaves, o Modo Criptográfico 2 será usado. O Modo Criptográfico 2 é uma implementação criptográfica atualizada e aprimorada do AD RMS. Ele é compatível com o RSA 2048 para assinatura e criptografia e oferece suporte ao SHA-256 para assinatura.

- Se você usar o Active Directory (AD) RMS para obter as chaves, o Modo Criptográfico 1 ou o Modo Criptográfico 2 será utilizado. O método utilizado depende de sua implantação do AD RMS no local. O Modo Criptográfico 1 é a implementação criptográfica original do AD RMS. Ele é compatível com o RSA 1024 para assinatura e criptografia e oferece suporte ao SHA-1 para assinatura. Esse modo continua a receber suporte de todas as versões atuais do RMS.

Para obter mais informações, consulte [AD RMS Cryptographic Modes](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)).
  
**P. Por que algumas mensagens criptografadas dizem que vêm de Office365@messaging.microsoft.com?**
  
Quando uma resposta criptografada é enviada do portal de criptografia ou pelo aplicativo Visualizador de OME, o endereço de email de envio é definido como Office365@messaging.microsoft.com, porque a mensagem criptografada é enviada por meio de um ponto de extremidade da Microsoft. Isso ajuda a impedir que mensagens criptografadas sejam marcadas como spam. O nome exibido no email e o endereço do portal de criptografia não são alterados por causa desse rótulo. Além disso, esse rótulo só se aplica às mensagens enviadas pelo portal, não por qualquer outro cliente de email.
  
 **P. Sou um assinante Exchange Criptografia Hospedada (EHE). Onde posso saber mais sobre a atualização para Criptografia de Mensagens do Office 365?**
  
Todos os clientes do EHE foram atualizados para a Criptografia de Mensagens do Office 365. Para obter mais informações, visite Exchange Centro de Atualização de [Criptografia Hospedado.](../security/defender-365-security/exchange-online-protection-overview.md)
  
 **P. Preciso abrir URLs, endereços IP ou portas no firewall da minha organização para dar suporte Criptografia de Mensagens do Office 365?**
  
Sim. É preciso adicionar URLs do Exchange Online à lista de permissões da organização para habilitar a autenticação para mensagens criptografadas pela Criptografia de Mensagem do Office 365. Para ver uma lista Exchange Online URLs, consulte [Microsoft 365 URLs e intervalos de endereços IP.](../enterprise/urls-and-ip-address-ranges.md)
  
 **P. Para quantos destinatários posso enviar uma mensagem Microsoft 365 criptografada?**
  
O limite de destinatários é de 500 destinatários por mensagem ou, quando combinado após a  expansão da lista de distribuição, 11.980 caracteres no campo Para da mensagem, o que ocorrer primeiro.
  
 **P. É possível revogar uma mensagem enviada para um destinatário específico?**
  
Não. Não é possível revogar uma mensagem para uma pessoa específica depois que ela for enviada.
  
 **P. Posso exibir um relatório de mensagens criptografadas que foram recebidas e lidas?**
  
Não há um relatório que mostre se uma mensagem criptografada foi exibida, mas há relatórios Microsoft 365 disponíveis que você pode aproveitar para determinar o número de mensagens que corresponderam a uma regra de fluxo de emails específica (também conhecida como regra de transporte), por exemplo.
  
 **P. O que a Microsoft faz com as informações que forneço por meio do Portal do OME e do aplicativo Visualizador do OME?**
  
A [Office 365 de](https://privacy.microsoft.com/privacystatement) privacidade do Portal de Criptografia de Mensagens fornece informações detalhadas sobre o que a Microsoft faz e não faz com suas informações privadas.

**P. O que faço se não receber o código de passagem único depois de solicitá-lo?**

Primeiro, verifique a pasta lixo eletrônico ou spam em seu cliente de email. As configurações DKIM e DMARC para sua organização podem fazer com que esses emails terminem filtrados como spam.

Em seguida, verifique a quarentena no Centro de Conformidade & Segurança. Muitas vezes, as mensagens que contêm um código de passagem única, especialmente as primeiras que sua organização recebe, terminam em quarentena.