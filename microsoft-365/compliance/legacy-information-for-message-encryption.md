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
description: Saiba como fazer a transição de arquivos herdados para a OME (criptografia de mensagem do Office 365) para sua organização.
ms.openlocfilehash: bf64d7991a843d2fd3d4f5f927eaa5c4bfef921c
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738028"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Informações herdadas de Criptografia de Mensagens do Office 365

Se você ainda não tiver movido sua organização para os novos recursos do OME, mas já tiver implantado o OME, as informações deste artigo se aplicam à sua organização. A Microsoft recomenda que você faça um plano para migrar para os novos recursos do OME assim que for razoável para sua organização. Para obter instruções, consulte [configurar novos recursos de criptografia de mensagem do Office 365 criados com base na proteção de informações do Azure](set-up-new-message-encryption-capabilities.md). Se quiser saber mais sobre como os novos recursos funcionam primeiro, confira criptografia de [mensagem do Office 365](ome.md). O restante deste artigo refere-se ao comportamento OME antes do lançamento dos novos recursos do OME.
  
Com a criptografia de mensagem do Office 365, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A criptografia de mensagem do Office 365 funciona com o Outlook.com, Yahoo, Gmail e outros serviços de email. A criptografia de mensagens de email ajuda a garantir que somente os destinatários pretendidos possam exibir o conteúdo da mensagem.
  
Aqui estão alguns exemplos:
  
- Um funcionário do banco envia instruções de cartão de crédito aos clientes

- Um representante da companhia de seguros fornece detalhes de política aos clientes

- Um corretor de hipoteca solicita informações financeiras de um cliente para um aplicativo de empréstimo

- Um provedor de assistência médica envia informações de assistência médica para pacientes

- Um advogado envia informações confidenciais para um cliente ou outro advogado

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Como a criptografia de mensagens do Office 365 funciona sem os novos recursos

A criptografia de mensagem do Office 365 é um serviço online desenvolvido no Microsoft Azure Rights Management (Azure RMS). Com o Azure RMS, os administradores podem definir regras de fluxo de email para determinar as condições de criptografia. Por exemplo, uma regra pode exigir a criptografia de todas as mensagens endereçadas a um destinatário específico.
  
Quando alguém envia uma mensagem de email no Exchange Online que corresponde a uma regra de criptografia, a mensagem é enviada com um anexo HTML. O destinatário abre o anexo HTML e segue as instruções para exibir a mensagem criptografada no portal de criptografia de mensagem do Office 365. O destinatário pode optar por exibir a mensagem entrando em uma conta da Microsoft ou em um trabalho ou escola associado ao Office 365 ou usando um código de passagem única. Ambas as opções ajudam a garantir que somente o destinatário pretendido pode exibir a mensagem criptografada. Esse processo é muito diferente para os novos recursos do OME.
  
O diagrama a seguir resume a passagem de uma mensagem de email pelo processo de criptografia e de descriptografia.
  
![Diagrama mostrando o caminho de um email criptografado](../media/O365-Office365MessageEncryption-Concept.png)
  
Para obter mais informações, consulte [Service Information for Legacy Office 365 Message Encryption antes do lançamento dos novos recursos do ome](legacy-information-for-message-encryption.md#LegacyServiceInfo).
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definindo regras de fluxo de email para a criptografia de mensagem do Office 365 que não usam os novos recursos do OME

Para habilitar a criptografia de mensagem do Office 365 sem os novos recursos, os administradores do Exchange Online e do Exchange Online Protection definem as regras de fluxo de email do Exchange. Essas regras determinam sob quais condições as mensagens de email devem ser criptografadas, bem como as condições para remover a criptografia de mensagens. Quando uma ação de criptografia é definida para uma regra, o serviço executa a ação em todas as mensagens que correspondam às condições de regra antes de enviar as mensagens.

As regras de fluxo de emails são flexíveis, permitindo que você combine condições para que possa atender a requisitos específicos de segurança em uma única regra. Por exemplo, você pode criar uma regra para criptografar todas as mensagens que contenham palavras-chave específicas e que sejam endereçadas a destinatários externos. A Criptografia de Mensagens do Office 365 também criptografa os emails de respostas dos destinatários e é possível criar uma regra para descriptografar essas respostas para a comodidade dos seus usuários de email. Dessa forma, os usuários em sua organização não precisarão entrar no portal de criptografia para exibir respostas.
  
Para obter mais informações sobre como criar regras de fluxo de email do Exchange, consulte [definir regras para a criptografia de mensagem do Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Use o Eat para criar uma regra de fluxo de emails para criptografar mensagens de email sem os novos recursos do OME

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** do \> **Exchange**.

4. No Eat, vá para regras de **fluxo de email** \>  e selecione **novo** ![ novo ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **criar uma nova regra**. Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Em **nome**, digite um nome para a regra, como criptografar email para DrToniRamos@hotmail.com.

6. Em **Aplicar esta regra se**, selecione uma condição e digite um valor, se necessário. Por exemplo, para criptografar mensagens enviadas a DrToniRamos@hotmail.com:

   1. Em **Aplicar esta regra se**, selecione **o destinatário é**.

   2. Escolha um nome existente na lista de contatos ou digite um novo endereço de email na caixa **verificar nomes**.

      - Para selecionar um nome existente, escolha-o na lista e clique em **OK**.

      - Para inserir um novo nome, digite um endereço de email na caixa **verificar nomes** e selecione **verificar nomes** \> **OK**.

7. Para adicionar mais condições, escolha **mais opções** e selecione **Adicionar condição** e selecione na lista.

   Por exemplo, para aplicar a regra apenas se o destinatário estiver fora da sua organização, selecione **Adicionar condição** e selecione **o destinatário é externo/interno** \> **fora da organização** \> **OK**.

8. Para habilitar a criptografia sem usar os novos recursos do ome, em **faça o seguinte**, selecione **Modificar a segurança da mensagem** \> **aplique a versão anterior do ome** e, em seguida, escolha **salvar**.

   Se você receber um erro de que o licenciamento do IRM não está habilitado, então você não está usando o OME herdado.

9. Opcion Escolha **Adicionar ação** para especificar outra ação.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Usar o PowerShell do Exchange Online para criar uma regra de fluxo de emails para criptografar mensagens de email sem os novos recursos do OME

1. Conecte-se ao PowerShell do Exchange Online. Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Crie uma regra usando o cmdlet **New-TransportRule** e defina o parâmetro _ApplyOME_ para `$true` .

   Este exemplo requer que todas as mensagens de email enviadas para DrToniRamos@hotmail.com devem ser criptografadas.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   Onde

   - O nome exclusivo da nova regra é "criptografar regra para Dr Toni ramos".
   - O parâmetro _SentTo_ especifica os destinatários da mensagem (identificados por nome, endereço de email, nome diferenciado, etc.). Neste exemplo, o destinatário é identificado pelo endereço de email "DrToniRamos@hotmail.com".
   - O parâmetro _SentToScope_ especifica a localização dos destinatários da mensagem. Neste exemplo, a caixa de correio do destinatário está no hotmail e não faz parte da organização, portanto, o valor `NotInOrganization` é usado.

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Remover a criptografia de respostas de email criptografadas sem os novos recursos do OME

Quando os usuários de email enviam mensagens criptografadas, os destinatários dessas mensagens podem responder com respostas criptografadas. Você pode criar regras de fluxo de email para remover automaticamente a criptografia das respostas para que os usuários de email em sua organização não precisem entrar no portal de criptografia para exibi-las. Você pode usar os cmdlets Eat ou Windows PowerShell para definir essas regras. Você pode descriptografar mensagens enviadas de dentro da sua organização ou mensagens que são respostas a mensagens enviadas de dentro da sua organização. Você não pode descriptografar mensagens criptografadas de fora da sua organização.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Use o Eat para criar uma regra para remover a criptografia de respostas de email criptografadas sem os novos recursos do OME

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** do \> **Exchange**.

4. No Eat, vá para regras de **fluxo de email** \>  e selecione **novo** ![ novo ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **criar uma nova regra**. Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Em **nome**, digite um nome para a regra, como remover criptografia de emails de entrada.

6. Em **aplicar esta regra, se** selecionar as condições em que a criptografia deve ser removida das mensagens, como **o destinatário está localizado** \> **dentro da organização**.

7. Em **faça o seguinte**, selecione **Modificar a segurança da mensagem** \> **remover a versão anterior do ome**.

8. Clique em **Salvar**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Usar o PowerShell do Exchange Online para criar uma regra para remover a criptografia de respostas de email criptografadas sem os novos recursos do OME

1. Conecte-se ao PowerShell do Exchange Online. Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Crie uma regra usando o cmdlet **New-TransportRule** e defina o parâmetro _RemoveOME_ para `$true` .

   Este exemplo remove a criptografia de todos os emails enviados para destinatários na organização.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   Onde

   - O nome exclusivo da nova regra é "remover a criptografia de emails de entrada".
   - O parâmetro _SentToScope_ especifica a localização dos destinatários da mensagem. Neste exemplo, o valor value `InOrganization` é usado, o que indica uma das seguintes opções:
     - O destinatário é uma caixa de correio, usuário de email, grupo ou pasta pública habilitada para email em sua organização.
     - O endereço de email do destinatário está em um domínio aceito configurado como um domínio autoritativo ou um domínio de retransmissão interno em sua organização, _e_ a mensagem foi enviada ou recebida através de uma conexão autenticada.

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule).

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>Enviar, exibir e responder a mensagens criptografadas sem os novos recursos

Com a criptografia de mensagem do Office 365, as mensagens de email são criptografadas automaticamente, com base em regras definidas pelo administrador. Um email que possui uma mensagem criptografada chega à caixa de entrada do destinatário com um arquivo HTML anexado.
  
Os destinatários seguem instruções na mensagem para abrir o anexo e autenticar usando uma conta da Microsoft ou um trabalho ou escola associado ao Office 365. Se os destinatários não tiverem uma das contas, eles serão direcionados para criar uma conta da Microsoft que permitirá que eles entrem para exibir a mensagem criptografada. Como alternativa, os destinatários podem optar por obter um código de passagem única para exibir a mensagem. Após entrar ou usar um código de passagem única, os destinatários podem exibir a mensagem descriptografada e enviar uma resposta criptografada.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalizar mensagens criptografadas com a criptografia de mensagem do Office 365

Como administrador de proteção do Exchange Online e do Exchange Online, você pode personalizar suas mensagens criptografadas. Por exemplo, você pode adicionar a marca e o logotipo da sua empresa, especificar uma introdução e adicionar texto de aviso de isenção de responsabilidade em mensagens criptografadas e no portal em que os destinatários exibem suas mensagens criptografadas. Usando cmdlets do Windows PowerShell, você pode personalizar os seguintes aspectos da experiência de visualização dos destinatários de mensagens de email criptografadas.

- Texto introdutório do email que contém a mensagem criptografada

- Texto do aviso de isenção de responsabilidade do email que contém a mensagem criptografada

- Texto do portal que aparecerá no portal de visualização da mensagem

- Logotipo que será exibido na mensagem de email e no portal de visualização

Você também pode reverter para a aparência padrão a qualquer momento.
  
O exemplo a seguir mostra um logotipo personalizado para a ContosoPharma no anexo de email:

> [!div class="mx-imgBorder"]
> ![Exemplo da página de exibição de mensagem criptografada](../media/TA-OME-3attachment2.jpg)
  
**Para personalizar as mensagens de email de criptografia e o portal de criptografia com a marca da sua organização**
  
1. Conecte-se ao Exchange Online usando o PowerShell remoto, conforme descrito em [Connect to Exchange Online using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Use o cmdlet Set-OMEConfiguration conforme descrito aqui: [set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b) ou use a tabela a seguir para orientação.

   **Opções de personalização de criptografia**

   | Para personalizar este recurso da experiência com criptografia | Utilize estes comandos do Windows PowerShell |
   |:-----|:-----|
   |Texto padrão que acompanha as mensagens de email criptografadas  <br/> O texto padrão é exibido acima das instruções para a exibição de mensagens criptografadas  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
   |Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
   |Texto que aparece na parte superior do portal de exibição do email criptografado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
   |Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de arquivo com suporte: .png, .jpg, .bmp ou .tiff  <br/> Tamanho ideal do arquivo de logotipo: menos que 40 KB  <br/> Tamanho ideal da imagem de logotipo: 170 pixels x 70 pixels  <br/> |

**Para remover as personalizações de marca de mensagens de email de criptografia e do portal de criptografia**
  
1. Conecte-se ao Exchange Online usando o PowerShell remoto, conforme descrito em [Connect to Exchange Online using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Use o cmdlet Set-OMEConfiguration conforme descrito aqui: [set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). Para remover as personalizações da marca da sua organização dos valores DisclaimerText, EmailText e PortalText, defina o valor como uma cadeia de caracteres vazia,  `""` . Para todos os valores de imagem, como logotipo, defina o valor como  `"$null"` .

   **Opções de personalização de criptografia**

   | Para reverter esse recurso da experiência de criptografia para o texto e a imagem padrões | Utilize estes comandos do Windows PowerShell |
   |:-----|:-----|
   |Texto padrão que acompanha as mensagens de email criptografadas  <br/> O texto padrão é exibido acima das instruções para a exibição de mensagens criptografadas  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
   |Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Exemplo:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
   |Texto que aparece na parte superior do portal de exibição do email criptografado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Exemplo reverter para o padrão:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
   |Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Exemplo reverter para o padrão:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Informações de serviço para a criptografia de mensagens herdada do Office 365 antes do lançamento dos novos recursos do OME
<a name="LegacyServiceInfo"> </a>

A tabela a seguir fornece detalhes técnicos para o serviço de criptografia de mensagem do Office 365 antes do lançamento dos novos recursos do OME.
  
| Detalhes do serviço | Descrição |
|:-----|:-----|
|Requisitos do dispositivo cliente  <br/> |As mensagens criptografadas podem ser visualizadas em qualquer dispositivo cliente, desde que o anexo HTML possa ser aberto em um navegador moderno compatível com Postagem de Formulário.  <br/> |
|Conformidade com algoritmos de criptografia e Normas Federais de Processamento de Informações (FIPS)  <br/> |A Criptografia de Mensagens do Office 365 usa as mesmas chaves de criptografia do Windows Information Rights Management (IRM) e dá suporte ao Modo Criptográfico 2 (chave 2K para RSA e chave de 256 bits para sistemas SHA-1). Para obter mais informações sobre os modos de criptografia do IRM subjacentes, consulte [modos criptográficos do AD RMS](https://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).  <br/> |
|Tipos de mensagem suportados  <br/> |A Criptografia de Mensagens do Office 365 é suportada apenas para itens que possuem uma identificação de classe de mensagem de **IPM.Note**. Para obter mais informações, consulte [tipos de item e classes de mensagens](https://msdn.microsoft.com/library/office/ff861573.aspx).  <br/> |
|Limites de tamanhos de mensagens  <br/> |A Criptografia de Mensagens do Office 365 pode criptografar mensagens de até 25 megabytes. Para obter mais detalhes sobre os limites de tamanho de mensagens, consulte [limites do Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).  <br/> |
|Políticas de retenção de email do Exchange Online  <br/> |O Exchange Online não armazena as mensagens criptografadas.  <br/> |
|Suporte de idioma para a Criptografia de Mensagens do Office 365  <br/> | A criptografia de mensagem do Office 365 suporta idiomas Microsoft 365, da seguinte maneira:  <br/>  As mensagens de email de entrada e os arquivos HTML anexados são localizados com base nas configurações de idioma do remetente.  <br/>  O portal de visualização está localizado com base nas configurações do navegador do destinatário.  <br/>  O corpo (conteúdo) da mensagem criptografada não está localizado.  <br/> |
|Informações de privacidade para o Portal OME e o aplicativo do Visualizador OME  <br/> |A [Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) fornece informações detalhadas sobre o que a Microsoft faz e não faz com suas informações particulares.  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>Perguntas frequentes sobre o OME herdado
<a name="LegacyServiceInfo"> </a>

Você tem dúvidas sobre a criptografia de mensagens do Office 365? Veja algumas respostas. Se você não encontrar o que precisa, consulte o [Microsoft Tech Community Forums for Office 365](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365).
  
 **T. Meus usuários enviam mensagens de email criptografadas para destinatários fora da organização. Há algo que os destinatários externos precisam fazer para ler e responder a mensagens de email criptografadas com a criptografia de mensagem do Office 365?**
  
Destinatários fora da sua organização que recebem mensagens criptografadas pela Microsoft 365 podem exibi-las de duas maneiras:
  
- Entrando com uma conta da Microsoft ou uma conta corporativa ou de estudante associada ao Office 365.

- Usando um código de passagem única.

 **T. As mensagens criptografadas da Microsoft 365 estão armazenadas na nuvem ou nos servidores Microsoft?**
  
Não, as mensagens criptografadas são mantidas no sistema de email do destinatário e, quando o destinatário abre a mensagem, ela é temporariamente publicada para exibição nos servidores Microsoft. As mensagens não são armazenadas lá.
  
 **P. Posso personalizar mensagens de email criptografadas com minha marca?**
  
Sim. É possível usar os cmdlets do Windows PowerShell para personalizar o texto padrão exibido na parte superior da mensagem de email criptografada, o texto do aviso de isenção de responsabilidade e o logotipo que você deseja usar nas mensagens de email e no portal de criptografia. Este recurso agora está disponível no OMEv2. Para obter detalhes, consulte [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **P. O serviço exige uma licença para cada usuário da organização?**
  
A licença é obrigatória para os usuários da organização que enviam emails criptografados.
  
 **P. São exigidas assinaturas para os destinatários externos?**
  
Não, os destinatários externos não necessitam de uma assinatura para ler ou responder mensagens criptografadas.
  
 **T. Como a criptografia de mensagem do Office 365 é diferente dos RMS (Rights Management Services)?**
  
O RMS fornece recursos de proteção de direitos de informação para os emails internos de uma organização fornecendo modelos internos, como: não encaminhar e confidencial da empresa. A Criptografia de Mensagens do Office 365 é compatível com a criptografia de mensagens de email para mensagens enviadas a destinatários externos e internos.
  
 **T. Como a criptografia de mensagem do Office 365 é diferente de S/MIME?**
  
Basicamente, o S/MIME é uma tecnologia de criptografia do lado do cliente e exige uma infraestrutura de publicação e de gerenciamento de certificados complicada. A criptografia de mensagem do Office 365 usa regras de fluxo de emails (também conhecidas como regras de transporte) e não depende de publicação de certificado.
  
 **P. Posso ler as mensagens criptografadas em dispositivos móveis?**
  
Sim, você pode exibir mensagens no Android e no iOS baixando os aplicativos do Visualizador do OME no Google Play Store e na Apple App Store. Abra o anexo em HTML no aplicativo Visualizador do OME e, em seguida, siga as instruções para abrir sua mensagem criptografada. Para outros dispositivos móveis, você poderá abrir o anexo em HTML se o cliente de email for compatível com a Postagem de Formulário.
  
 **P. As respostas e as mensagens encaminhadas são criptografadas?**
  
Sim. As respostas continuam a ser criptografadas durante todo o decurso do thread.
  
 **T. A criptografia de mensagem do Office 365 fornece localização?**
  
O conteúdo HTML e de emails de entrada é localizado com base nas configurações de email do remetente. O portal de exibição é localizado com base nas configurações do navegador do destinatário. No entanto, o próprio corpo (conteúdo) da mensagem criptografada não é localizado.
  
 **T. Qual método de criptografia é usado para a criptografia de mensagem do Office 365?**
  
A criptografia de mensagem do Office 365 usa o Rights Management Services (RMS) como sua infraestrutura de criptografia. O método de criptografia usado depende do local que você obtém as chaves do RMS usadas para criptografar e descriptografar mensagens.
  
- Se você usar o Microsoft Azure RMS para obter as chaves, o modo criptográfico 2 será usado. O Modo Criptográfico 2 é uma implementação criptográfica atualizada e aprimorada do AD RMS. Ele é compatível com o RSA 2048 para assinatura e criptografia e oferece suporte ao SHA-256 para assinatura.

- Se você usar o Active Directory (AD) RMS para obter as chaves, o Modo Criptográfico 1 ou o Modo Criptográfico 2 será utilizado. O método utilizado depende de sua implantação do AD RMS no local. O Modo Criptográfico 1 é a implementação criptográfica original do AD RMS. Ele é compatível com o RSA 1024 para assinatura e criptografia e oferece suporte ao SHA-1 para assinatura. Esse modo continua a receber suporte de todas as versões atuais do RMS.

Para obter mais informações, consulte [modos criptográficos do AD RMS](https://go.microsoft.com/fwlink/p/?LinkId=398616).
  
**P. Por que algumas mensagens criptografadas dizem que elas vêm do** Office365@messaging.microsoft.com?
  
Quando uma resposta criptografada é enviada do portal de criptografia ou pelo aplicativo Visualizador de OME, o endereço de email de envio é definido como Office365@messaging.microsoft.com, porque a mensagem criptografada é enviada por meio de um ponto de extremidade da Microsoft. Isso ajuda a impedir que mensagens criptografadas sejam marcadas como spam. O nome exibido no email e o endereço do portal de criptografia não são alterados por causa desse rótulo. Além disso, esse rótulo só se aplica às mensagens enviadas pelo portal, não por qualquer outro cliente de email.
  
 **T. Eu sou assinante do Exchange Hosted Encryption (EHE). Onde posso saber mais sobre a atualização para a criptografia de mensagem do Office 365?**
  
Todos os clientes do EHE foram atualizados para a Criptografia de Mensagens do Office 365. Para obter mais informações, visite o [centro de atualização de criptografia hospedado do Exchange](https://go.microsoft.com/fwlink/p/?LinkID=511077).
  
 **T. Preciso abrir qualquer URL, endereço IP ou portas no firewall da minha organização para dar suporte à criptografia de mensagens do Office 365?**
  
Sim. É preciso adicionar URLs do Exchange Online à lista de permissões da organização para habilitar a autenticação para mensagens criptografadas pela Criptografia de Mensagem do Office 365. Para obter uma lista de URLs do Exchange Online, confira [URLs e intervalos de endereços IP do Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).
  
 **T. A quantos destinatários posso enviar uma mensagem criptografada 365 da Microsoft?**
  
O limite de destinatários é de 500 destinatários por mensagem ou, quando combinado após a expansão da lista de distribuição, 11.980 caracteres no campo para da mensagem, o **que** vier primeiro.
  
 **P. É possível revogar uma mensagem enviada para um destinatário específico?**
  
Não. Não é possível revogar uma mensagem para uma determinada pessoa após ela ser enviada.
  
 **P. Posso exibir um relatório de mensagens criptografadas que foram recebidas e lidas?**
  
Não há um relatório que mostra se uma mensagem criptografada foi exibida, mas há relatórios do Microsoft 365 disponíveis que você pode aproveitar para determinar o número de mensagens que corresponderam a uma regra de fluxo de emails específica (também conhecida como regra de transporte), por exemplo.
  
 **P. O que a Microsoft faz com as informações que forneço por meio do Portal do OME e do aplicativo Visualizador do OME?**
  
A [declaração de privacidade do portal de criptografia de mensagens do Office 365](https://privacy.microsoft.com/privacystatement) fornece informações detalhadas sobre o que a Microsoft faz e não faz com suas informações particulares.

**T. O que fazer se eu não receber o código de passagem única depois de solicitá-lo?**

Primeiro, verifique a pasta de lixo eletrônico ou spam em seu cliente de email. As configurações do DKIM e do DMARC para sua organização podem fazer com que esses emails terminem de ser filtrados como spam.

Em seguida, verifique a quarentena no centro de conformidade de & de segurança. Muitas vezes, as mensagens que contêm um código de passagem única, especialmente as primeiras que sua organização recebe, terminam em quarentena.
