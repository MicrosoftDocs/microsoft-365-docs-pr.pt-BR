---
title: Use DKIM para email em seu domínio personalizado no Office 365, 2048 bits, 1024 bits, etapas, Como funciona, SPF, DMARC
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Resumo: este artigo descreve como usar o DomainKeys Identified Mail (DKIM) com o Office 365 para garantir que os sistemas de email de destino confiem em mensagens enviadas de seu domínio personalizado.'
ms.openlocfilehash: 496089ff46d66df3382895626831023610c706be
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957156"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>Use o DKIM para validar emails enviados de seu domínio personalizado no Office 365

 **Resumo:** Este artigo descreve como você usa o DomainKeys Identified Mail (DKIM) com o Office 365 para garantir que os sistemas de email de destino confiem em mensagens enviadas de saída de seu domínio personalizado.

Você deve usar o DKIM, além do SPF e do DMARC, para ajudar a evitar que spoofers enviem mensagens que pareçam que são provenientes de seu domínio. O DKIM possibilita adicionar uma assinatura digital no cabeçalho de mensagens de email enviadas. Parece complicado, mas não é. Quando você configura o DKIM, autoriza seu domínio a associar, ou fazer login, seu nome a uma mensagem de email usando a autenticação de criptografia. Sistemas de email que recebem emails de seu domínio podem usar essa assinatura digital para ajudar a determinar se os emails recebidos são legítimos.

Basicamente, você usa uma chave privada para criptografar o cabeçalho no email de saída do seu domínio. Publique uma chave pública nos registros DNS do seu domínio que os servidores de recebimento possam então usar para decodificar a assinatura. Eles usam a chave pública para confirmar que as mensagens realmente vêm de você e não de alguém que está *falsificando* seu domínio.

O Office 365 configura automaticamente o DKIM para domínios iniciais de “onmicrosoft.com”. Isso significa que não é preciso fazer nada para configurar o DKIM para qualquer nome de domínio inicial (por exemplo, litware.onmicrosoft.com). Para saber mais sobre domínios, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

Você também pode optar por não fazer nada sobre o DKIM em relação ao seu domínio personalizado. Se você não configurar o DKIM para o seu domínio personalizado, o Office 365 criará um par de chaves privada e pública, habilitará a assinatura do DKIM e configurará a política padrão do Office 365 para o seu domínio personalizado. Embora isso seja abrangente o suficiente para a maioria dos clientes do Office 365, você deve configurar manualmente o DKIM para o seu domínio personalizado nas seguintes circunstâncias:

- Você tem mais de um domínio personalizado no Office 365

- For configurar o DMARC também (recomendado)

- Quiser ter controle sobre sua chave privada

- Quiser personalizar seus registros CNAME

- Configure as chaves do DKIM para emails provenientes de um domínio de terceiros, por exemplo, se você usar um programa de email em massa terceirizado.

Neste artigo:

- [Como o DKIM funciona melhor do que a SPF para evitar a falsificação maliciosa no Office 365](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [O que você precisa fazer para configurar manualmente o DKIM no Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Para configurar o DKIM para mais de um domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Desabilitar a política de assinatura do DKIM para um domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Comportamento padrão para o DKIM e o Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer spoof de, emails em nome de seu domínio personalizado](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Próximas etapas: depois de configurar o DKIM para o Office 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>Como o DKIM funciona melhor do que o SPF para evitar a falsificação maliciosa no Office 365
<a name="HowDKIMWorks"> </a>

A SPF adiciona informações a um envelope de mensagem, mas o DKIM realmente criptografa uma assinatura dentro do cabeçalho da mensagem. Ao encaminhar uma mensagem, partes de seu envelope podem ser removidas pelo servidor de encaminhamento. Como a assinatura digital permanece com a mensagem de email porque faz parte do cabeçalho do email, o DKIM funciona mesmo quando uma mensagem é encaminhada conforme mostrado no exemplo a seguir.

![Diagrama que mostra uma mensagem encaminhada passando pela autenticação DKIM onde a verificação de SPF falha](../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

Neste exemplo, se você tivesse apenas publicado um registro TXT SPF do seu domínio, o servidor de email do destinatário poderia ter marcado seu email como spam e gerado um resultado positivo falso. A adição do DKIM neste cenário reduz o resultado positivo falso de spam. Como o DKIM depende de criptografia de chave pública para autenticar, e não apenas de endereços IP, é considerado uma forma muito mais forte de autenticação que o SPF. Recomendamos usar o SPF e o DKIM, bem como o DMARC, em sua implantação.

Detalhes fundamentais: o DKIM usa uma chave privada para inserir uma assinatura criptografada nos cabeçalhos das mensagens. A domínio que assina, ou domínio de saída, é inserido como o valor do campo **d=** no cabeçalho. O domínio que verifica, ou domínio do destinatário, usa esse campo **d=** para procurar a chave pública no DNS e autenticar a mensagem. Se a mensagem for verificada, passa na verificação do DKIM.

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits
<a name="1024to2048DKIM"> </a>

Já que tanto o número de bits 1024 e o 2048 têm suporte para chaves DKIM, essas instruções mostrarão como atualizar a chave de 1024 para 2048 bits. As etapas a seguir são para dois casos de uso, escolha o que melhor se adapta à sua configuração.

1. Quando você **já tiver o DKIM configurado**, alterne o número de bits da seguinte maneira:
    1. [Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (O cmdlet é proveniente do Exchange Online.)
    1. E, em seguida, execute o seguinte cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`

1. Ou para uma **nova implementação do DKIM**:
    1. [Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (Este é um cmdlet do Exchange Online.)
    1. Execute o seguinte cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`

Mantenha-se conectado ao Office 365 para *verificar* a configuração.

2. Execute o cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`

> [!TIP]
>Essa nova chave de 2048 bits entra em vigor no RotateOnDate e enviará emails com a chave 1024 bits provisoriamente. Após quatro dias, você poderá testar novamente com a chave de 2048 bits (ou seja, quando a rotação entrar em vigor no segundo seletor).

Se você deseja alternar para o segundo seletor, suas opções são: a) permitir que o serviço do Office 365 alterne o seletor e atualize para o número de bits 2048 nos próximos 6 meses, ou b) após 4 dias confirmando que número de bits 2048 está em uso, manualmente alterne a segunda chave de seletor usando o cmdlet apropriado listado acima.

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>O que você precisa fazer para configurar manualmente o DKIM no Office 365
<a name="SetUpDKIMO365"> </a>

Para configurar o DKIM, execute estas etapas:

- [Publicar dois registros CNAME para o seu domínio personalizado no DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Habilitar a assinatura DKIM para o seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Publicar dois registros CNAME para o seu domínio personalizado no DNS
<a name="Publish2CNAME"> </a>

Para cada domínio para o qual você deseja adicionar uma assinatura de DKIM no DNS, é preciso publicar dois registros CNAME.

Execute os seguintes comandos para criar os registros do seletor:

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

Crie CNAMEs referenciados na saída Get-DkimSigningConfig

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```

O Office 365 executa a rotação de chaves automática usando os dois registros estabelecidos. Se você provisionou domínios personalizados em adição ao domínio inicial no Office 365, deve publicar dois registros CNAME para cada domínio adicional. Portanto, se você tem dois domínios, deve publicar dois registros CNAME adicionais e assim por diante.

Use o seguinte formato para os registros CNAME.

> [!IMPORTANT]
> Se você for um dos nossos clientes GCC High, nós calculamos o _domainGuid_ de maneira diferente! Em vez de procurar o registro MX do seu _initialDomain_ para calcular o _domainGuid_, ele é calculado diretamente a partir do domínio personalizado. Por exemplo, se seu domínio personalizado for "contoso.com", o domainGuid vai se tornar "contoso-com", os pontos serão substituídos por um traço. Portanto, independentemente de qual registro MX seu initialDomain apontar, você sempre usará o método acima para calcular o domainGuid para usar em seus registros CNAME.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Onde:

- Para o Office 365, os seletores sempre serão "seletor1" ou "seletor2".

- O _domainGUID_ é igual ao _domainGUID_ no registro MX personalizado para o seu domínio personalizado, que aparece antes de mail.protection.outlook.com. Por exemplo, no seguinte registro MX para o domínio contoso.com, o _domainGUID_ é contoso-com:

    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- O _initialDomain_ é o domínio que você usou quando se inscreveu no Office 365. Os domínios iniciais sempre terminam em onmicrosoft.com. Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

Por exemplo, se você tiver o domínio inicial cohovineyardandwinery.onmicrosoft.com e dois domínios personalizados, cohovineyard.com e cohowinery.com, precisará configurar dois registros CNAME para cada domínio adicional, totalizando quatro registros CNAME.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> É importante criar o segundo registro, mas apenas um dos seletores pode estar disponível no momento da criação. Em essência, o segundo seletor pode apontar para um endereço que ainda não foi criado. Ainda recomendamos que você crie o segundo registro CNAME, pois a rotação de chaves será contínua e você não precisará executar as etapas manuais por conta própria.

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>Habilitar a assinatura DKIM para o seu domínio personalizado no Office 365
<a name="EnableDKIMinO365"> </a>

Depois de publicar os registros CNAME no DNS, você está pronto para habilitar a assinatura de DKIM através do Office 365. É possível fazer isso por meio do centro de administração do Microsoft 365 ou usando o PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>Para habilitar a assinatura DKIM para o seu domínio personalizado por meio do centro de administração

1. [Entrar no Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) com sua conta corporativa ou de estudante.

2. Selecione o ícone do inicializador de aplicativos no canto superior esquerdo e escolha **Administrador**.

3. No painel de navegação inferior à esquerda, expanda **Administrador** e escolha **Exchange**.

4. Vá para **Proteção** \> **DKIM**.

5. Selecione o domínio para o qual você deseja habilitar o DKIM e, para **Assinar mensagens deste domínio com assinaturas DKIM**, escolha **Habilitar**. Repita essa etapa para cada domínio personalizado.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Para habilitar a assinatura DKIM para o seu domínio personalizado usando o PowerShell

1. [Conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Execute o seguinte comando:

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   Em que _domínio_ é o nome do domínio personalizado para o qual você deseja habilitar a assinatura DKIM.

   Por exemplo, para o domínio contoso.com:

    ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>Para confirmar que a assinatura de DKIM está configurada adequadamente para o Office 365

Aguarde alguns minutos antes de prosseguir com essas etapas para confirmar que você configurou o DKIM corretamente. Isso permite que as informações do DKIM sobre o domínio sejam distribuídas por toda a rede.

- Envie uma mensagem de uma conta do seu domínio do Office 365 habilitado com DKIM para outra conta de email, como outlook.com ou Hotmail.com.

- Não use uma conta aol.com para fins de teste. A AOL pode ignorar a verificação de DKIM se a verificação de SPF passar. Isso anula o teste.

- Abra a mensagem e examine o cabeçalho. Instruções para exibir o cabeçalho da mensagem variam dependendo do seu cliente de mensagens. Para instruções sobre como visualizar cabeçalhos de mensagens no Outlook, confira [Visualizar cabeçalhos de mensagens de email](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).

  A mensagem assinada com DKIM conterá o nome do host e o domínio definidos quando você publicou as entradas CNAME. A mensagem terá uma aparência similar à do exemplo:

  ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Procure pelo cabeçalho Authentication-Results. Embora cada serviço receptor use um formato ligeiramente diferente para carimbar as mensagens recebidas, o resultado deve incluir algo parecido com **DKIM=pass** ou **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>Para configurar o DKIM para mais de um domínio personalizado no Office 365
<a name="DKIMMultiDomain"> </a>

Se em algum momento no futuro você decidir adicionar outro domínio personalizado e quiser habilitar o DKIM para o novo domínio, deve executar as etapas deste artigo para cada domínio. Especificamente, execute todas as etapas em [O que você precisa fazer para configurar manualmente o DKIM no Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>Desabilitar a política de assinatura do DKIM para um domínio personalizado no Office 365
<a name="DisableDKIMSigningPolicy"> </a>

Desabilitar a política de assinatura não desabilita completamente o DKIM. Após um período de tempo, o Office 365 aplicará automaticamente a política padrão do Office 365 ao seu domínio. Para saber mais, confira [Comportamento padrão para o DKIM e o Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Para desabilitar a política de assinatura do DKIM usando o Windows PowerShell

1. [Conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Execute um dos seguintes comandos para cada domínio para o qual você deseja desabilitar a assinatura de DKIM.

    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   Por exemplo:

    ```powershell
    $p = Get-DkimSigningConfig -Identity contoso.com
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   Ou

    ```powershell
    Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
    ```

    Em que o _número_ é o índice da política. Por exemplo:

    ```powershell
    Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a>Comportamento padrão para o DKIM e o Office 365
<a name="DefaultDKIMbehavior"> </a>

Se você não habilitar o DKIM, o Office 365 cria automaticamente uma chave pública de DKIM de 1024 bits para seu domínio padrão e a chave privada associada que é armazenada internamente em nosso datacenter. Por padrão, o Office 365 usa uma configuração de assinatura padrão para domínios que não tem uma política aplicada. Isso significa que se você não configurar o DKIM por conta própria, o Office 365 usa a política e as chaves padrão que ele cria para habilitar o DKIM para seu domínio.

Além disso, se você desabilitar a assinatura DKIM após ativá-la, depois de um período de tempo o Office 365 aplicará automaticamente a política padrão do Office 365 para o seu domínio.

No exemplo a seguir, suponha que o DKIM de fabrikam.com foi habilitado pelo Office 365, não pelo administrador do domínio. Isso significa que os CNAMEs necessários não existem no DNS. Assinaturas DKIM para email deste domínio terão uma aparência similar a esta:

```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

Neste exemplo, o nome de host e o domínio contêm os valores para os quais o CNAME apontaria se a assinatura de DKIM para fabrikam.com tivesse sido ativada pelo administrador do domínio. Eventualmente, cada mensagem enviada do Office 365 será assinada com DKIM. Se você mesmo habilitar o DKIM, o domínio será o mesmo que o do campo de endereço De:, neste caso fabrikam.com. Caso contrário, os domínios não corresponderão entre si e, em vez disso, será usado o domínio inicial da sua organização. Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer falsificar, emails em nome de seu domínio personalizado
<a name="SetUp3rdPartyspoof"> </a>

Alguns provedores de serviço de email em massa, ou provedores de software como serviço, permitem que você configure as chaves DKIM para o email originado de seu serviço. Isso exige a coordenação entre sua empresa e a empresa terceirizada para configurar os registros DNS necessários. Não há duas organizações que fazem isso exatamente da mesma maneira. Em vez disso, o processo depende totalmente da organização.

Um exemplo de mensagem mostrando um DKIM configurado adequadamente para contoso.com e bulkemailprovider.com pode parecer com este:

```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

Neste exemplo, para obter este resultado:

1. O provedor de email em massa deu à Contoso uma chave pública de DKIM.

2. A Contoso publicou a chave de DKIM em seu registro DNS.

3. Ao enviar emails, o Provedor de Email em Massa assina a chave com a chave privada correspondente. Ao fazer isso, o Provedor de Email em Massa anexa a assinatura DKIM ao cabeçalho da mensagem.

4. Sistemas de recebimento de email executam uma verificação de DKIM autenticando o valor DKIM-Signature d=\<domínio\> em relação ao domínio no campo de endereço From: (5322.From) da mensagem. Neste exemplo, os valores são correspondentes:

    remetente@**contoso.com**

    d=**contoso.com**

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>Próximas etapas: depois de configurar o DKIM para o Office 365
<a name="DKIMNextSteps"> </a>

Embora o DKIM tenha sido projetado para ajudar a evitar a falsificação, ele funciona melhor com SPF e DMARC. Depois que você configurar o DKIM, se já não tiver configurado o SPF, deve fazê-lo. Para obter uma introdução rápida à SPF e para configurá-la rapidamente, veja [Configurar a SPF no Office 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md). A seguir, confira [Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md). [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md), que inclui a sintaxe e os campos de cabeçalho usados pelo Office 365 para verificações de DKIM.
