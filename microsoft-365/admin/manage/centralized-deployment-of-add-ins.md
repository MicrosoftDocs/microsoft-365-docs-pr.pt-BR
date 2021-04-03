---
title: Determinar se a Implantação Centralizada de complementos funciona para sua organização
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine se o locatário e os usuários atendem aos requisitos, para que você possa usar a Implantação Centralizada para implantar os complementos do Office.
ms.openlocfilehash: 1516a10932158ba137f58900e0c19c5fea3bd119
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580949"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinar se a Implantação Centralizada de complementos funciona para sua organização

A Implantação Centralizada é a maneira recomendada e mais rica em recursos para a maioria dos clientes implantar os complementos do Office para usuários e grupos em sua organização. Se você for um administrador, use essa orientação para determinar se sua organização e usuários atendem aos requisitos para que você possa usar a Implantação Centralizada.

A Implantação Centralizada oferece os seguintes benefícios:
  
- Um administrador global pode atribuir um complemento diretamente a um usuário, a vários usuários por meio de um grupo ou a todos na organização.
    
- Quando o aplicativo do Office relevante é iniciado, o complemento baixa automaticamente. Se o add-in dá suporte a comandos de add-in, o complemento aparece automaticamente na faixa de opções dentro do aplicativo do Office.
    
- Os complementos não aparecerão mais para os usuários se o administrador desligar ou excluir o complemento ou se o usuário for removido do Azure Active Directory ou de um grupo ao qual o add-in é atribuído.

A Implantação Centralizada dá suporte a três plataformas de área de trabalho Aplicativos do Windows, Mac e Online do Office. A Implantação Centralizada também oferece suporte para iOS e Android (Somente para Os Complementos do Outlook Mobile).

Pode levar até 24 horas para um complemento aparecer para cliente para todos os usuários.
  
## <a name="requirements"></a>Requisitos

A implantação centralizada de complementos exige que os usuários usem SKUs do Microsoft 365 Enterprise: E3/E5/F3 ou SKUs Corporativos: Business Basic, Business Standard, Business Premium (e são assinados no Office usando sua ID organizacional) e têm caixas de correio do Exchange Online e do Exchange Online ativas. Seu diretório de assinatura deve estar ou federado para o Azure Active Directory.
Você pode exibir requisitos específicos para o Office e o Exchange abaixo ou usar o Verificador de Compatibilidade de [Implantação Centralizado](#centralized-deployment-compatibility-checker).

A Implantação Centralizada não é compatível com:
  
- Suplementos que visam o Word, Excel ou o PowerPoint no Office 2013 
- Um serviço de diretório local
- Implantação de um add-in para uma caixa de correio do Exchange on-prem
- Implantação de suplemento no SharePoint  
- Aplicativos do Teams
- Implantação do Modelo de Objeto de Componente (COM) ou Visual Studio ferramentas para os complementos do Office (VSTO).
- Implantações do Microsoft 365 que não incluem o Exchange Online, como SKUs: Microsoft 365 Apps for Business e Microsoft 365 Apps for Enterprise.

### <a name="office-requirements"></a>Requisitos do Office

- Para os complementos do Word, do Excel e do PowerPoint, os usuários devem estar usando um dos seguintes:
  - Em um dispositivo Windows, versão 1704 ou posterior do Microsoft 365 Enterprise SKUs: E3/E5/F3 ou SKUs Corporativos: Business Basic, Business Standard, Business Premium.
  - Em um Mac, versão 15.34 ou posterior.

- Para o Outlook, seus usuários devem estar usando um dos seguintes: 
  - Versão 1701 ou posterior do Microsoft 365 Enterprise SKUs: E3/E5/F3 ou Business SKUs: Business Basic, Business Standard, Business Premium.
  - Versão 1808 ou posterior do Office Professional Plus 2019 ou Office Standard 2019.
  - Versão 16.0.4494.1000 ou posterior do Office Professional Plus 2016 (MSI) ou Office Standard 2016 (MSI)\*
  - Versão 15.0.4937.1000 ou posterior do Office Professional Plus 2013 (MSI) ou Office Standard 2013 (MSI)\*
  - Versão 16.0.9318.1000 ou posterior do Office 2016 para Mac 
- Versão 2.75.0 ou posterior do Outlook mobile para iOS 
- Versão 2.2.145 ou posterior do Outlook mobile para Android 
    
    *As versões MSI do Outlook mostram os complementos instalados pelo administrador na faixa de opções apropriada do Outlook, não na seção "Meus complementos".

### <a name="exchange-online-requirements"></a>Requisitos do Exchange Online

O Microsoft Exchange armazena os manifestos de complemento no locatário da sua organização. O administrador que está implantando os complementos e os usuários que recebem esses complementos devem estar em uma versão do Exchange Online que oferece suporte à autenticação OAuth.
  
Fale com o administrador do Exchange da sua organização para saber qual configuração está sendo usada. Para verificar a conectividade por usuário do OAuth, use o cmdlet do PowerShell [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity). 


### <a name="centralized-deployment-compatibility-checker"></a>Verificação de Compatibilidade de Implantação Centralizada

Usando o Verificador de Compatibilidade de Implantação Centralizada, você pode verificar se os usuários em seu locatário estão definidos para usar a Implantação Centralizada para Word, Excel e PowerPoint. O Verificador de Compatibilidade não é necessário para o suporte do Outlook. Baixe o verificador de compatibilidade [aqui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Executar o checker de compatibilidade
  
1. Inicie uma janela PowerShell.exe elevada.
    
2. Execute o seguinte comando:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Execute o **comando Invoke-CompatabilityCheck:**

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Este comando solicita  *_tenantDomain_* (por exemplo, *TailspinToysIncorporated.onmicrosoft. </span> com*) e  *_credenciais tenantAdmin_* (use suas credenciais de administrador global) e solicita consentimento.
    
   > [!NOTE]
   > O verificador pode ser concluído em minutos ou horas, dependendo da quantidade de usuários no locatário. 
  
Quando a ferramenta conclui a execução, ela gera um arquivo de saída no formato .csv. O arquivo é salvo em **C:\windows\system32** por padrão. O arquivo de saída contém as seguintes informações:
  
- Nome de usuário
    
- ID de usuário (o endereço de email do usuário)
    
- Implantação Centralizada pronta, se os itens restantes forem verdadeiros
    
- Plano do Office - O plano do Office para o que eles estão licenciados
    
- Office ativado - Se ele ativou o Office
    
- Caixa de correio com suporte - Se ele usa uma caixa de correio habilitada para OAuth

> [!NOTE]
> A autenticação multifator não é suportada ao usar o módulo PowerShell de Implantação Central.
  
## <a name="user-and-group-assignments"></a>Atribuições de usuário e grupo

O recurso implantação centralizada atualmente dá suporte à maioria dos grupos com suporte do Azure Active Directory, incluindo grupos do Microsoft 365, listas de distribuição e grupos de segurança.
  
> [!NOTE]
> Os grupos de segurança não habilitados por email não têm suporte no momento. 
  
A Implantação Centralizada dá suporte a atribuições para usuários individuais, grupos e todos no locatário. A Implantação Centralizada é compatível com usuários em grupos de nível superior ou grupos sem grupos-pai, mas não é compatível com usuários em grupos aninhados ou grupos com grupos-pai.
   
Examine o exemplo a seguir em que Sara, Maria Eduarda e o grupo do Departamento de Vendas são atribuídos a um suplemento. Como o Departamento de Vendas da Costa Oeste é um grupo aninhado, Humberto e Fábio não estão atribuídos a um suplemento.
  
![Diagrama do departamento de vendas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Determinar se um grupo contém grupos aninhados

A maneira mais fácil de detectar se um grupo contém grupos aninhados é exibir o cartão de visita do grupo no Outlook. Se você inserir o nome do grupo no campo **Para** de um email e, em seguida, selecionar o nome do grupo quando ele for resolvido, ele mostrará se ele contém usuários ou grupos aninhados. No exemplo abaixo, a guia **Membros** do cartão de visita do Outlook para o Grupo de Teste não mostra usuários nem grupos, apenas dois subgrupos. 
  
![Guia Membros do cartão de visita do Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
É possível fazer a consulta inversa resolvendo o grupo para ver se ele é membro de algum grupo. No exemplo abaixo, na guia **Associação** do cartão de visita do Outlook, é possível ver que o Subgrupo 1 é membro do Grupo de Teste. 
  
![Guia Associação do cartão de visita do Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
Se preferir, use a API do Graph do Azure Active Directory para executar consultas para localizar a lista de grupos dentro de um grupo. Para saber mais, veja [Operações em grupos | Referência da API do Graph](/previous-versions/azure/ad/graph/api/groups-operations).
  
### <a name="contacting-microsoft-for-support"></a>Entrar em contato com a Microsoft para obter suporte

Se você ou seus usuários encontrarem problemas para carregar o complemento enquanto usam aplicativos do Office para a Web (Word, Excel, etc.), que foram implantados centralmente, talvez seja necessário entrar em contato com o suporte da Microsoft ( saiba[como](../contact-support-for-business-products.md)). Forneça as seguintes informações sobre seu ambiente do Microsoft 365 no tíquete de suporte.
  
|**Plataforma**|**Informações de depuração**|
|:-----|:-----|
|Office  <br/> | Registros de Charles/Fiddler  <br/>  ID do locatário ( [saiba como](/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  CorrelationID. Exibir a origem de uma das páginas do office e procurar o valor da ID de correlação e enviá-la para dar suporte a:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Clientes avançados (Windows, Mac)  <br/> | Registros de Charles/Fiddler  <br/>  Criar números do aplicativo cliente (preferencialmente como uma captura de tela de **Arquivo/Conta**)  <br/> |
