---
title: Adicionar um domínio a uma Windows PowerShell cliente para parceiros DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Resumo: use o PowerShell para Microsoft 365 adicionar um nome de domínio alternativo a um locatário de cliente existente.'
ms.openlocfilehash: 5ebbe11da9a93669945e7e3b096ce7afa18b5d3a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288426"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Adicionar um domínio a uma locação do cliente com o Windows PowerShell para parceiros com permissão de acesso delegado (DAP)

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode criar e associar novos domínios ao seu cliente com o PowerShell para Microsoft 365 mais rápido do que usar o Centro de administração do Microsoft 365.

Os Parceiros com Permissão de Acesso Delegada (DAP) são parceiros da Agregação e dos Provedores de Soluções em Nuvem (CSP). Muitas vezes, eles são provedores de rede ou de telecomunicações para outras empresas. Eles agrupam Microsoft 365 assinaturas em suas ofertas de serviço para seus clientes. Quando eles vendem uma assinatura de Microsoft 365, eles são automaticamente concedidos permissões Administer On Behalf Of (AOBO) para as empresas de cliente, para que possam administrar e relatar as permissões do cliente.
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

Os procedimentos neste tópico exigem que você se conecte ao Conexão [para Microsoft 365 com o PowerShell](connect-to-microsoft-365-powershell.md).

Você também precisa ter as credenciais de administrador de locatários do parceiro.

Você também precisará das seguintes informações:

- É necessário o nome de domínio totalmente qualificado (FQDN) escolhido pelo cliente.

- É necessária a **TenantId** do cliente.

- O FQDN deve ser registrado com um registrador de Serviço de Nomes de Domínio da Internet (DNS), como o GoDaddy. Para saber mais sobre como registrar publicamente um nome de domínio, confira [Como comprar um nome de domínio](../admin/get-help-with-domains/buy-a-domain-name.md).

- Você precisa saber como adicionar um registro TXT à zona DNS registrada do seu registrador de DNS. Para obter mais informações sobre como adicionar um registro TXT, consulte [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). Se esses procedimentos não funcionarem, localize os procedimentos do seu registrador de DNS.

## <a name="create-domains"></a>Criar domínios

 Os clientes provavelmente vão solicitar a criação de domínios adicionais para associar às suas locações, uma vez que não pretendem ter o<domínio>.onmicrosoft.compadrão como o domínio principal que representa sua identidade corporativa mundialmente. Este procedimento lhe orienta na criação de um novo domínio associado à locação do cliente.

> [!NOTE]
> Para executar algumas dessas operações, a conta de administrador  de parceiro  com a sua assinatura deve ser definida como Administração completa para a configuração Atribuir acesso administrativo às empresas com suporte encontrada nos detalhes da conta de administrador no Centro de administração do Microsoft 365. Para obter mais informações sobre como gerenciar funções de administrador de parceiros, consulte [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).

### <a name="create-the-domain-in-azure-active-directory"></a>Criar o domínio no Azure Active Directory

Esse comando cria o domínio no Azure Active Directory, mas não o associa ao domínio registrado publicamente. Isso acontece quando você prova que possui o domínio registrado publicamente para a Microsoft Microsoft 365 para empresas.

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Obter os dados do registro de verificação TXT de DNS

 Microsoft 365 gerará os dados específicos que você precisa colocar no registro de verificação TXT DNS. Para obter os dados, execute o seguinte comando.

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Isso lhe dará saída como:

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> Você vai precisar desse texto para criar o registro TXT na zona DNS registrada publicamente. Não deixe de copiá-lo e salvá-lo.

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Adicionar um registro TXT à zona DNS registrada publicamente

Antes Microsoft 365 começar a aceitar tráfego direcionado para o nome de domínio registrado publicamente, você deve provar que é o seu próprio e ter permissões de administrador para o domínio. Para provar que você é o proprietário do domínio, crie um registro TXT nele. Um registro TXT não altera nada em seu domínio e pode ser excluído depois que for provado que você possui o domínio. Para criar os registros TXT, siga os procedimentos em [Adicionar registros DNS para conectar seu domínio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). Caso esses procedimentos não funcionem, localize os procedimentos do seu registrador de DNS.

Confirme a criação bem-sucedida do registro TXT por meio do nslookup. Execute a seguinte sintaxe.

```console
nslookup -type=TXT <FQDN of registered domain>
```

Isso lhe dará saída como:

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>Validar a propriedade de domínio em Microsoft 365

Nesta última etapa, você valida para Microsoft 365 que você possui o domínio registrado publicamente. Após esta etapa, Microsoft 365 começará a aceitar o tráfego roteado para o novo nome de domínio. Para concluir a criação do domínio e o processo de registro, execute o seguinte comando.

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Este comando não retornará nenhuma saída; portanto, para confirmar se ele funcionou, execute-o.

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Isso retornará algo parecido com o seguinte

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a>Confira também

[Ajuda para parceiros](https://go.microsoft.com/fwlink/p/?LinkID=533477)
