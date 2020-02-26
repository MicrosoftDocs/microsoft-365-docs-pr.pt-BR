---
title: Determinar se a implantação centralizada de suplementos funciona para a sua organização
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine se o locatário do Office 365 e os usuários atendem aos requisitos, para que você possa usar a implantação centralizada para implantar os suplementos do Office.
ms.openlocfilehash: b5cd04100b025705d29f86a07ec5f6aece259a8a
ms.sourcegitcommit: 1f04eb8a32aed8571ac37bcfef61e0d0ef181eda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42278757"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinar se a implantação centralizada de suplementos funciona para a sua organização

A Implantação Centralizada é a forma recomendada e com recursos mais avançados que a maioria dos clientes usa para implantar suplementos do Office para usuários e grupos na sua organização do Office 365. Se você for um administrador, use este guia para determinar se o locatário e os usuários atendem aos requisitos para que você possa usar a implantação centralizada.
A implantação centralizada oferece suporte a Windows, Mac, iOS, Android e aplicativos do Office Online.
Pode levar até 12 horas para que um suplemento seja exibido para o cliente para todos os usuários.
  
## <a name="requirements"></a>Requisitos

A implantação centralizada de suplementos exige que os usuários estejam usando o Office 365 ProPlus (e estejam conectados ao Office usando a respectiva ID organizacional) e tenham o Exchange Online e caixas de correio ativas do Exchange Online. O diretório da sua assinatura deve ser ou federado no Azure Active Directory.
Você pode exibir requisitos específicos para o Office e o Exchange abaixo ou usar o [Verificador de compatibilidade de implantação centralizada do office 365](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).

A Implantação Centralizada não é compatível com:
  
- Suplementos que visam o Word, Excel ou o PowerPoint no Office 2013
    
- Um serviço de diretório local
    
- Implantação de suplemento no SharePoint  

- Aplicativos do teams
   
- Implantação de suplementos do COM (Component Object Model) ou VSTO (Visual Studio Tools para Office)
    
- Implantações do Office 365 que não incluem o Exchange, como o Office 365 Business

### <a name="office-requirements"></a>Requisitos do Office

- Para suplementos do Word, Excel e PowerPoint, seus usuários devem estar usando um dos seguintes:
  - Em um dispositivo do Windows, versão 1704 ou posterior do Office 365 ProPlus.
  - Em um Mac, versão 15,34 ou posterior.
      - No iOS (somente iPad), a versão 2.9.18010804 ou posterior.
- Para o Outlook, seus usuários devem estar usando um dos seguintes: 
  - Versão 1701 ou posterior do Office 365 ProPlus.
  - Versão 1808 ou posterior do Office Professional Plus 2019 ou Office Standard 2019.
  - Versão 16.0.4494.1000 ou posterior do Office Professional Plus 2016 (MSI) ou Office Standard 2016 (MSI)\*
  - Versão 15.0.4937.1000 ou posterior do Office Professional Plus 2013 (MSI) ou Office Standard 2013 (MSI)\*
  - Versão 16.0.9318.1000 ou posterior do Office 2016 para Mac 
- Versão 2.75.0 ou posterior do Outlook Mobile para iOS 
- Versão 2.2.145 ou posterior do Outlook Mobile para Android 
    
    * As versões MSI do Outlook mostram os suplementos instalados pelo administrador na faixa de opções do Outlook apropriada, e não na seção "meus suplementos".
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a>Verificar se o Office 365 ProPlus está instalado

Para usar o Office 365 ProPlus, um usuário deve ter uma conta do Office 365 e deve ter uma licença atribuída. Confira mais informações em [Visão geral do Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).

A maneira mais simples de detectar se um usuário tem o Office 365 ProPlus instalado e o está usando recentemente é usar o relatório de ativações do Microsoft Office, que está disponível no centro de administração do Microsoft 365. Ele fornece uma lista de todos os usuários que ativaram o Office 365 ProPlus nos últimos 7, 30, 90 ou 180 dias. Para fins de implantação centralizada, as ativações da área de trabalho para Windows ou Mac são as colunas importantes no relatório. É possível exportar o relatório para Excel. Veja mais informações sobre o relatório em [Relatórios do Office 365 no Centro de Administração - Ativações do Microsoft Office](../activity-reports/microsoft-office-activations.md).
  
Se não quiser usar o relatório de ativações, você pode pedir a um usuário para abrir um aplicativo do Office, como o Word, em sua máquina e, em seguida, escolher **conta**de **arquivo** \> . Em **Informações do Produto** deve haver **Produto de Assinatura** e **Microsoft Office 365 ProPlus**, como mostra a imagem a seguir.

![Informações de produto em um aplicativo do Office](../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
Encontre ajuda para o Office 365 ProPlus em [Dicas de solução de problemas para o Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).


### <a name="exchange-online-requirements"></a>Requisitos do Exchange Online

O Microsoft Exchange armazena os manifestos do suplemento no locatário da sua organização. Os suplementos de implantação de administrador e os usuários que recebem esses suplementos devem estar em uma versão do Exchange Online que oferece suporte à autenticação OAuth. Por padrão, o multilocatário do Exchange e implantações do 
  
Fale com o administrador do Exchange da sua organização para saber qual configuração está sendo usada. Para verificar a conectividade por usuário do OAuth, use o cmdlet do PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351). 


### <a name="office-365-centralized-deployment-compatibility-checker"></a>Verificador de Compatibilidade para Implantação Centralizada do Office 365

Com o Verificador de Compatibilidade para Implantação Centralizada do Office 365, você pode verificar se configurou os usuários no locatário para usar a Implantação Centralizada para Word, Excel e PowerPoint. O Verificador de Compatibilidade não é necessário para o suporte do Outlook. Baixe o verificador de compatibilidade [aqui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Executar o verificador de compatibilidade
  
1. Inicie uma janela do PowerShell. exe com privilégios elevados.
    
2. Execute o seguinte comando:

```powershell
Import-Module O365CompatibilityChecker
```
    
3. Execute o comando **Invoke-CompatabilityCheck** :

```powershell
Invoke-CompatibilityCheck
```
   que solicita *_TenantDomain_* (por exemplo, *TailspinToysIncorporated. onmicrosoft.</span> com*) e *_TenantAdmin_* credenciais (use suas credenciais de administrador global) e, em seguida, solicitações de consentimento.
    
> [!NOTE]
> O verificador pode ser concluído em minutos ou horas, dependendo da quantidade de usuários no locatário. 
  
Quando a ferramenta conclui a execução, ela gera um arquivo de saída no formato .csv. O arquivo é salvo em **C:\Windows\System32** por padrão. O arquivo de saída contém as seguintes informações:
  
- Nome de usuário
    
- ID de usuário (o endereço de email do usuário)
    
- Implantação Centralizada pronta, se os itens restantes forem verdadeiros
    
- Plano do Office – o plano do Office para o qual eles estão licenciados
    
- Office ativado - Se ele ativou o Office
    
- Caixa de correio com suporte - Se ele usa uma caixa de correio habilitada para OAuth


  
## <a name="user-and-group-assignments"></a>Atribuições de usuário e grupo

Atualmente, o recurso Implantação Centralizada oferece suporte à maioria dos grupos com suporte do Azure Active Directory, como Grupos do Office 365, listas de distribuição e grupos de segurança.
  
> [!NOTE]
> Os grupos de segurança não habilitados por email não têm suporte no momento. 
  
A implantação centralizada oferece suporte a atribuições para usuários individuais, grupos e todos no locatário. A Implantação Centralizada é compatível com usuários em grupos de nível superior ou grupos sem grupos-pai, mas não é compatível com usuários em grupos aninhados ou grupos com grupos-pai.
   
Examine o exemplo a seguir em que Sara, Maria Eduarda e o grupo do Departamento de Vendas são atribuídos a um suplemento. Como o Departamento de Vendas da Costa Oeste é um grupo aninhado, Humberto e Fábio não estão atribuídos a um suplemento.
  
![Diagrama do departamento de vendas](../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Determinar se um grupo contém grupos aninhados

A maneira mais fácil de detectar se um grupo contém grupos aninhados é exibir o cartão de visita do grupo no Outlook. Se você inserir o nome do grupo no campo **para** de um email e selecionar o nome do grupo quando ele resolver, ele mostrará se ele contém usuários ou grupos aninhados. No exemplo abaixo, a guia **Membros** do cartão de visita do Outlook para o Grupo de Teste não mostra usuários nem grupos, apenas dois subgrupos. 
  
![Guia Membros do cartão de visita do Outlook](../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
É possível fazer a consulta inversa resolvendo o grupo para ver se ele é membro de algum grupo. No exemplo abaixo, na guia **Associação** do cartão de visita do Outlook, é possível ver que o Subgrupo 1 é membro do Grupo de Teste. 
  
![Guia Membros do cartão de visita do Outlook](../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
Se preferir, use a API do Graph do Azure Active Directory para executar consultas para localizar a lista de grupos dentro de um grupo. Para saber mais, veja [Operações em grupos | Referência da API do Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Entrar em contato com a Microsoft para obter suporte

Se você ou seus usuários encontrarem problemas ao carregar o suplemento durante o uso dos aplicativos do Office para a Web (Word, Excel, etc.), que foram implantados centralmente, talvez seja necessário entrar em contato com o suporte da Microsoft ([saiba como](../contact-support-for-business-products.md)). Forneça as informações a seguir sobre o ambiente do Office 365 no tíquete de suporte.
  
|**Plataforma**|**Informações de depuração**|
|:-----|:-----|
|Office  <br/> | Registros de Charles/Fiddler  <br/>  ID do locatário ( [saiba como](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))  <br/>  CorrelationID. Exibir a origem de uma das páginas do Office e procurar o valor de ID de correlação e enviá-lo ao suporte:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Clientes avançados (Windows, Mac)  <br/> | Registros de Charles/Fiddler  <br/>  Números de compilação do aplicativo cliente (preferencialmente como captura de tela de **arquivo/conta**)  <br/> |
   

