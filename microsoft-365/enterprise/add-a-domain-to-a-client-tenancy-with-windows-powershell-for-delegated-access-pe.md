---
title: Adicionar um domínio a um local de cliente com o Windows PowerShell para parceiros DAP
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
description: 'Resumo: Use o PowerShell para Microsoft 365 para adicionar um nome de domínio alternativo a um locatário existente do cliente.'
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687497"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Adicionar um domínio a uma locação do cliente com o Windows PowerShell para parceiros com permissão de acesso delegado (DAP)

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode criar e associar novos domínios à sua loja do cliente com o PowerShell para Microsoft 365 mais rápido do que usar o centro de administração do Microsoft 365.
  
Os Parceiros com Permissão de Acesso Delegada (DAP) são parceiros da Agregação e dos Provedores de Soluções em Nuvem (CSP). Muitas vezes, eles são provedores de rede ou de telecomunicações para outras empresas. Eles agrupam assinaturas do Microsoft 365 em suas ofertas de serviço para seus clientes. Ao vender uma assinatura do Microsoft 365, eles receberão automaticamente permissões de Administrar em Nome de (AOBO) para as empresas do cliente para que possam administrar e relatar as permissões do cliente.
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

Os procedimentos neste tópico exigem que você se conecte ao [Microsoft 365 com o PowerShell.](connect-to-microsoft-365-powershell.md)
  
Você também precisa ter as credenciais de administrador de locatários do parceiro.
  
Você também precisará das seguintes informações:
  
- É necessário o nome de domínio totalmente qualificado (FQDN) escolhido pelo cliente.
    
- É necessária a **TenantId** do cliente.
    
- O FQDN deve ser registrado com um registrador de Serviço de Nomes de Domínio da Internet (DNS), como o GoDaddy. Para saber mais sobre como registrar publicamente um nome de domínio, confira [Como comprar um nome de domínio](https://go.microsoft.com/fwlink/p/?LinkId=532541).
    
- Você precisa saber como adicionar um registro TXT à zona DNS registrada do seu registrador de DNS. Para obter mais informações sobre como adicionar um registro TXT, consulte Adicionar registros [DNS para conectar seu domínio.](https://go.microsoft.com/fwlink/p/?LinkId=532542) Se esses procedimentos não funcionarem, localize os procedimentos do seu registrador de DNS.
    
## <a name="create-domains"></a>Criar domínios

 Os clientes provavelmente vão solicitar a criação de domínios adicionais para associar às suas locações, uma vez que não pretendem ter o<domínio>.onmicrosoft.compadrão como o domínio principal que representa sua identidade corporativa mundialmente. Este procedimento lhe orienta na criação de um novo domínio associado à locação do cliente.
  
> [!NOTE]
> Para executar algumas dessas operações, a conta de administrador  do parceiro  com a que você entrar deve ser definida como Administração total para atribuir acesso administrativo a empresas às empresas às que você dá suporte à configuração encontrada nos detalhes da conta de administrador no Centro de administração do Microsoft 365. Para obter mais informações sobre como gerenciar funções de administrador de parceiros, [consulte Parceiros: Oferecer administração delegada.](https://go.microsoft.com/fwlink/p/?LinkId=532435) 
  
### <a name="create-the-domain-in-azure-active-directory"></a>Criar o domínio no Azure Active Directory

Esse comando cria o domínio no Azure Active Directory, mas não o associa ao domínio registrado publicamente. Isso acontece quando você provar que é o domínio registrado publicamente no Microsoft 365 para empresas.
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Obter os dados do registro de verificação TXT de DNS

 O Microsoft 365 gerará os dados específicos que você precisa colocar no registro de verificação TXT dns. Para obter os dados, execute o seguinte comando.
  
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

Antes que o Microsoft 365 comece a aceitar tráfego direcionado para o nome de domínio registrado publicamente, você deve provar que é o próprio e tem permissões de administrador para o domínio. Para provar que você é o proprietário do domínio, crie um registro TXT nele. Um registro TXT não altera nada em seu domínio e pode ser excluído depois que for provado que você possui o domínio. Para criar os registros TXT, siga os procedimentos em [Adicionar registros DNS para conectar seu domínio.](https://go.microsoft.com/fwlink/p/?LinkId=532542) Caso esses procedimentos não funcionem, localize os procedimentos do seu registrador de DNS.
  
Confirme a criação bem-sucedida do registro TXT por meio do nslookup. Execute a seguinte sintaxe.
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

Isso lhe dará saída como:
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a>Validar a propriedade do domínio no Microsoft 365

Nesta última etapa, você valida para o Microsoft 365 que é o domínio registrado publicamente. Após essa etapa, o Microsoft 365 começará a aceitar tráfego roteado para o novo nome de domínio. Para concluir a criação do domínio e o processo de registro, execute o seguinte comando. 
  
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

#### 

[Ajuda para parceiros](https://go.microsoft.com/fwlink/p/?LinkID=533477)

