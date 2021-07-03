---
title: Alterar nameservers para configurar Microsoft 365 com qualquer registrador de domínios
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Saiba como adicionar e configurar seu domínio no Microsoft 365 para que seus serviços, como email e Skype for Business Online, usem seu próprio nome de domínio.
ms.openlocfilehash: 1a65ca52b85c2cf2e4fc30e2a71e5930ae7a9a4d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287120"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Alterar nameservers para configurar Microsoft 365 com qualquer registrador de domínios

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.

Siga estas instruções para adicionar e configurar seu domínio no Microsoft 365 para que seus serviços como email e Teams usem seu próprio nome de domínio. Para fazer isso, você verificará seu domínio e alterará os nameservers do seu domínio para Microsoft 365 para que os registros DNS corretos possam ser definidos para você. Siga estas etapas se as instruções a seguir descreverem sua situação:

- Você tem seu próprio domínio e deseja defini-lo para trabalhar com Microsoft 365.

- Você deseja Microsoft 365 gerenciar seus registros DNS para você. Se preferir, é possível[ gerenciar seus próprios registros DNS ](../setup/add-domain.md).

## <a name="add-a-txt-or-mx-record-for-verification"></a>Adicionar um registro TXT ou MX para verificação

> [!NOTE]
> Você criará apenas um desses registros. O TXT é o tipo de registro preferencial, mas alguns provedores de host DNS não são compatíveis com ele. Nesse caso, você pode criar um registro MX como alternativa.

Antes de usar o seu domínio com o Microsoft 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova ao Microsoft 365 que você é o proprietário do domínio.

> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.

### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Encontre a área no site do provedor de hospedagem DNS onde você pode criar um novo registro

1. Entre no site do seu provedor de hospedagem DNS.

2. Escolha seu domínio.

3. Localize a página na qual você pode editar registros DNS para o seu domínio.

### <a name="create-the-record"></a>Criar o registro

Caso esteja criando um registro TXT ou um registro MX, siga um destes procedimentos:

**Se você criar um registro TXT, use estes valores:**

<br>

****

|Tipo de registro|Alias ou nome do host|Valor|TTL|
|---|---|---|---|
|TXT|Siga um destes procedimentos: Digite **@**, deixe o campo vazio ou digite o seu nome de domínio.  <p> **Observação:** hosts DNS diferentes têm requisitos diferentes para este campo.|MS = ms *XXXXXXXX* <p> **Observação**: esse é um exemplo. Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)|Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.|
|||||

**Se você criar um registro MX, use estes valores:**

<br>

****

|Tipo de registro|Alias ou nome do host|Valor|Prioridade|TTL|
|---|---|---|---|---|
|MX|Digite **@** ou seu nome de domínio. |MS=ms *XXXXXXXX* **Observação:** este é um exemplo. Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)|Para **Priority**, para evitar conflitos com o registro MX usado para o fluxo de email, use uma prioridade menor do que a prioridade de qualquer registro MX existente. Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)|Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.|
||||||

### <a name="save-the-record"></a>Salvar o registro

Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.

Quando o Microsoft 365 encontrar o registros TXT correto, o domínio será verificado.

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

2. Na página **Domínios**, clique no domínio que você está verificando.

3. Na página **Configuração**, clique em **Iniciar configuração**.

4. Na página **Verificar domínio**, marque **Verificar**.

> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio

Quando você chegar à última etapa do assistente de configuração de domínios no Microsoft 365, você terá uma tarefa restante. Para configurar seu domínio com serviços Microsoft 365, como email, você altera os registros de nameserver (ou NS Microsoft 365) do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do seu domínio. Em seguida, como Microsoft 365 hospeda seu DNS, os registros DNS necessários para seus serviços são definidos automaticamente para você. Você pode atualizar os registros de servidor de nomes por conta própria seguindo as etapas que seu registrador de domínio pode fornecer no conteúdo de Ajuda no site deles. Se você não estiver familiarizado com DNS, contate o suporte no registrador de domínios.

::: moniker range="o365-worldwide"

Para alterar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga estas etapas:

1. Encontre a área no site do registrador de domínios onde você pode alterar os nameservers para seu domínio ou uma área onde você pode usar nameservers personalizados.

2. Crie registros de nameserver ou edite os registros de nameserver existentes para corresponder aos seguintes valores:

    - Nameserver: ns1.bdm.microsoftonline.com
    - Segundo nameserver: ns2.bdm.microsoftonline.com
    - Terceiro nameserver: ns3.bdm.microsoftonline.com
    - Quarto nameserver: ns4.bdm.microsoftonline.com

   > [!TIP]
   > É melhor adicionar todos os quatro registros, mas se o registrador tiver suporte apenas para dois, adicione ns1.bdm.microsoftonline.com **e** **ns2.bdm.microsoftonline.com**.

3. Salve suas alterações.

> [!CAUTION]
> Quando você altera os registros NS do seu domínio para apontar para os Microsoft 365 de nomes, todos os serviços associados ao seu domínio são afetados. Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias. Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.

::: moniker-end

::: moniker range="o365-21vianet"

1. Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.

2. Crie dois registros de servidor de nomes ou edite os registros de servidor de nomes existentes para que eles correspondam aos seguintes valores:

   - Nameserver: ns1.dns.partner.microsoftonline.cn
   - Segundo nameserver: ns2.dns.partner.microsoftonline.cn

   > [!TIP]
   > Você deve usar pelo menos dois registros de nameserver. Se houver outros servidores de nomes listados, você poderá excluí-los ou alterá-los para ns3.dns.partner.microsoftonline.cn **e** **ns4.dns.partner.microsoftonline.cn**.

3. Salve suas alterações.

> [!CAUTION]
> Quando você altera os registros NS do seu domínio para apontar para o Office 365 operado por servidores de nomes da 21Vianet, todos os serviços associados ao seu domínio são afetados. Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias. Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.

::: moniker-end

Por exemplo, aqui estão algumas etapas adicionais que podem ser necessárias para a hospedagem de email e de site:

- Mova todos os endereços de email que usam seu domínio para Microsoft 365 antes de alterar seus registros NS.

- Você deseja adicionar um domínio atualmente usado com um site da Web, como www.fourthcoffee.com? Você pode seguir as etapas enquanto adiciona o domínio para manter seu site hospedado onde o site está hospedado agora para que as pessoas ainda possam chegar ao site depois que você alterar os registros NS do domínio para apontar para Microsoft 365.

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

2. Selecione um domínio na página **Domínios**.

3. Na página detalhes do domínio, selecione a **guia Registros DNS.**

4. Selecione **Adicionar registro**.

5. No painel **Adicionar um registro DNS personalizado,** na lista suspenso **Tipo,** selecione **A (Endereço)**.

6. Na caixa **Nome do Host ou Alias,** digite **@** .

7. Na caixa **Endereço IP,** digite o endereço IP estático para o site onde ele está hospedado no momento. Por exemplo, 172.16.140.1.

   > [!IMPORTANT]
   > Esse deve ser um _endereço_ IP estático para o site, não um _endereço_ IP dinâmico. Para garantir que você possa obter um endereço IP estático para seu site público, verifique com o site que hospeda seu site.

8. Se você quiser alterar a configuração TTL do registro, selecione um novo período de tempo na lista suspenso **TTL.** Caso contrário, continue para a etapa 9.

9. Selecione **Salvar**.

Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.

1. Selecione **Adicionar registro**.
2. No painel **Adicionar um registro DNS personalizado,** na lista suspenso **Tipo,** selecione **CNAME (Alias)**.
3. Na caixa **Nome do Host ou Alias,** digite **www**.
4. Na caixa **Pontos para endereço,** digite o FQDN (nome de domínio totalmente qualificado) para seu site. Por exemplo, **contoso.5om**.
5. Se você quiser alterar a configuração TTL do registro, selecione um novo período de tempo na lista suspenso **TTL.** Caso contrário, continue para a etapa 6.
6. Selecione **Salvar**.

Depois que os registros do nameserver são atualizados para apontar para a Microsoft, a configuração do domínio é concluída. O email é roteado para a Microsoft e o tráfego para seu endereço de site continua a ir para o host do site atual.'

> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio.

## <a name="related-content"></a>Conteúdo relacionado

[Adicionar registros DNS para conectar seu domínio](create-dns-records-at-any-dns-hosting-provider.md) (artigo)\
[Localizar e corrigir problemas após adicionar seu domínio ou registros DNS ](find-and-fix-issues.md) (artigo)\
[Gerenciar domínios](index.yml) (página de link)
