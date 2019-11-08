---
title: Proteger sites e arquivos do SharePoint Online
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- SPO_Content
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 'Resumo: recomendações de configuração para proteger arquivos no SharePoint Online e no Office 365.'
ms.openlocfilehash: 62b7227239c52f50f2dc437e1ddedc663a5bb01d
ms.sourcegitcommit: 6e01543b3fff50a28719478b19b644991ba7505a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38035701"
---
# <a name="secure-sharepoint-online-sites-and-files"></a>Proteger sites e arquivos do SharePoint Online

 **Resumo:** recomendações de configuração para proteger arquivos no SharePoint Online e no Office 365.
  
Este artigo fornece recomendações para configurar sites de equipe do SharePoint Online e proteção de arquivo que equilibra a segurança com facilidade de colaboração. Esse artigo define quatro configurações diferentes, começando com um site público dentro de sua organização com as políticas de compartilhamento abertas. Cada configuração adicional representa uma etapa significativa na proteção, mas a capacidade de acessar e colaborar com os recursos é reduzida ao conjunto de usuários relevantes. Use essas recomendações como um ponto de partida e ajuste as configurações para atender às necessidades da sua organização. 
  
As configurações nesse artigo se alinham às recomendações da Microsoft para três níveis de proteção de dados, identidades e dispositivos:
  
- Proteção de linha de base
    
- Proteção confidencial
    
- Proteção altamente confidencial
    
Para obter mais informações sobre essas camadas e recursos recomendados para cada camada, consulte os recursos a seguir. 
  
- [Proteção de identidade e dispositivo para o Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365IDP)
    
- [Soluções para proteção de arquivos do Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365fileprotect)
    
## <a name="capability-overview"></a>Visão geral da funcionalidade

As recomendações para sites de equipe do SharePoint Online traçam uma variedade de recursos do Microsoft 365. A ilustração a seguir mostra as configurações recomendadas para quatro sites de equipe do SharePoint Online.

![Configuração recomendada para sites do SharePoint](../media/SharePoint-site-configurations.png)

Conforme ilustrado:
  
- A proteção de linha de base inclui duas opções para sites de equipe do SharePoint Online — um site público e um site privado. Os sites públicos podem ser descobertos e acessados por qualquer pessoa na organização. Os sites privados podem ser descobertos e acessados apenas por membros do site. Essas configurações de site permitem o compartilhamento fora do grupo. 
    
- Os sites para proteção confidencial e altamente confidencial são sites privados com acesso limitado apenas a membros de grupos específicos.
    
- [Rótulos de retenção](../../compliance/labels.md) oferecem uma maneira para classificar arquivos em sites. Cada um dos sites de equipe do SharePoint Online é configurado para aplicar rótulos automaticamente aos arquivos nas bibliotecas de documentos com um rótulo de retenção padrão para o site. Correspondentes às quatro configurações de site, os rótulos nesse exemplo são Público Interno, Privado, Confidencial e Altamente Confidencial. Os usuários podem alterar os rótulos, mas essa configuração garante que todos os arquivos de recebem um rótulo padrão.
    
- As políticas DLP [(prevenção de perda de dados)](../../compliance/data-loss-prevention-policies.md) são configuradas para os rótulos de retenção Confidenciais e Altamente Confidenciais para avisar ou impedir os usuários quando tentam enviar esses tipos de arquivos para fora da organização.
    
- Se for necessário para sua situação, você pode usar [rótulos de confidencialidade](../../compliance/sensitivity-labels.md)para proteger arquivos altamente confidenciais com criptografia e permissões. Clientes da Proteção de Informações do Azure pode, usar  Rótulos da Proteção de Informações do Azure no centro de conformidade do Microsoft 365 e os rótulos serão sincronizados com o portal do Azure, caso seja escolhido executar a configuração adicional ou avançada. Os Rótulos de Proteção de Informações do Azure e os rótulos de confidencialidade do Office 365 são totalmente compatíveis entre si. Isso significa que, por exemplo, se você tiver um conteúdo rotulado pela Proteção de Informações do Azure, não será necessário reclassificar ou rotular novamente o conteúdo. Nem todos os clientes necessitam desse nível de proteção. 
    
## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a>Configurações para todo o locatário do SharePoint Online e OneDrive for Business

O SharePoint Online e OneDrive para Empresas incluem configurações para todo o locatário que afetam todos os sites e os usuários. Algumas dessas configurações também podem ser ajustadas no nível do site para serem mais restritivas (mas não menos). Esta seção discute as configurações para todo o locatário que afetam a segurança e a colaboração. 
  
### <a name="sharing"></a>Compartilhamento

Para esta solução, recomendamos as seguintes configurações para todo o locatário:
  
- Mantenha a política de configuração padrão que permite todo o compartilhamento com todos os tipos de conta, incluindo o compartilhamento anônimo.
    
- Configure os links anônimos para expirar, se desejado.
    
- Altere o tipo de link padrão para o compartilhamento para Interno. Isso ajuda a impedir o vazamento acidental de dados fora da sua organização.
    
Embora possa parecer contraintuitivo permitir o compartilhamento externo, essa abordagem fornece mais controle sobre o compartilhamento de arquivo em comparação com enviar os arquivos por email. O SharePoint Online e o Outlook trabalham juntos para fornecer a colaboração segura nos arquivos. 
  
- Por padrão, o Outlook compartilha um link para um arquivo em vez de enviar o arquivo por email. 
    
- O SharePoint Online e OneDrive for Business facilitam compartilhar links para arquivos com colaboradores que estão dentro e fora da sua organização
    
Você também tem controles para ajudar a controlar o compartilhamento externo. Por exemplo, você pode:
  
- Desabilitar um link de convidado anônimo.
    
- Revogar o acesso de usuário para um site.
    
- Ver quem tem acesso a um documento ou um site específico.
    
- Configurar os links de compartilhamento anônimos para expirarem (configuração de locatário).
    
- Limitar quem pode compartilhar fora da sua organização (configuração de locatário).
    
### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Usar o compartilhamento externo junto com a DLP (prevenção de perda de dados)

Se você não permitir o compartilhamento externo, os usuários com uma empresa encontrarão métodos e ferramentas alternativas. A Microsoft recomenda que você combine o compartilhamento externo com políticas DLP para proteger os arquivos confidenciais e altamente confidenciais.
  
### <a name="device-access-settings"></a>Configurações de acesso de dispositivo

As configurações de acesso de dispositivo do SharePoint Online e do OneDrive para Empresas permitem que você determine se o acesso é limitado apenas ao navegador (não é possível baixar os arquivos) ou se o acesso está bloqueado. Para obter informações, consulte [Controlar o acesso de dispositivos gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices). 

Para usar as configurações de acesso de dispositivo com as políticas de acesso condicional recomendadas no Azure Active Directory, confira [Recomendações de política para proteger os arquivos e sites do SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).
  
### <a name="onedrive-for-business"></a>OneDrive for Business

Visite essas configurações para decidir se deseja alterar as configurações padrão para sites do OneDrive para Empresas. Atualmente, as configurações de acesso de compartilhamento e de dispositivo estão duplicadas do Centro de administração do SharePoint Online e se aplicam a ambos os ambientes.
  
## <a name="sharepoint-team-site-configuration"></a>Configuração de site de equipe do SharePoint

A tabela a seguir resume a configuração para cada um dos sites de equipe descritos anteriormente neste artigo. Use essas configurações como recomendações de ponto de partida e ajuste as configurações e os tipos de site para atender às necessidades da sua organização. Nem toda organização precisa de todos os tipos de site. Somente um pequeno número de organizações requer a proteção altamente confidencial.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
||**Proteção de linha de base nº 1** <br/> |**Proteção de linha de base nº 2** <br/> |**Proteção confidencial** <br/> |**Altamente confidencial** <br/> |
|Descrição  <br/> |Abra a descoberta e a colaboração dentro da organização.  <br/> |Grupo e site particulares com o compartilhamento permitido fora do grupo.  <br/> |Site isolado, no qual os níveis de acesso são definidos pela associação em grupos específicos. O compartilhamento é permitido apenas para membros do site. A DLP avisa os usuários quando tenta enviar arquivos fora da organização.  <br/> |Criptografia de arquivo + site isolado e permissões com a Proteção de Informações do Azure. A DLP impede que os usuários enviem arquivos fora da organização.  <br/> |
|Site de equipe público ou privado  <br/> |Público  <br/> |Private  <br/> |Private  <br/> |Private  <br/> |
|Quem tem acesso?  <br/> |Todas as pessoas na organização, incluindo usuários convidados e usuários de B2B.  <br/> |Membros do site somente. Outros usuários podem solicitar acesso.  <br/> |Membros do site somente. Outros usuários podem solicitar acesso.  <br/> |Somente membros. Outros usuários não podem solicitar acesso.  <br/> |
|Controles de compartilhamento de nível de site  <br/> |Compartilhamento permitido com qualquer pessoa. Configurações padrão.  <br/> |Compartilhamento permitido com qualquer pessoa. Configurações padrão.  <br/> |Os membros não podem compartilhar o acesso ao site.  <br/> Os não membros podem solicitar acesso ao site, mas essas solicitações precisam ser atendidas por um administrador de site.  <br/> |Os membros não podem compartilhar o acesso ao site.  <br/> Os não membros não podem solicitar acesso ao site ou conteúdo.  <br/> |
|Controles de acesso de dispositivo de nível de site  <br/> |Sem controles adicionais.  <br/> |Sem controles adicionais.  <br/> |Impede que os usuários baixem arquivos para os dispositivos incompatíveis ou com domínio não associado. Isso permite o acesso somente para navegador de todos os outros dispositivos.  <br/> |Bloquear o download de arquivos para os dispositivos incompatíveis ou com domínio não associado.  <br/> |
|Rótulos de retenção  <br/> |Público interno  <br/> |Private  <br/> |Confidencial  <br/> |Altamente Confidencial  <br/> |
|Políticas DLP  <br/> |||Avisar os usuários quando enviar arquivos que são rotulados como Confidencial para fora da organização.  <br/> Para bloquear o compartilhamento externo de tipos de dados confidenciais, como números de cartão de crédito ou outros dados pessoais, você pode configurar políticas DLP adicionais para esses tipos de dados (incluindo tipos de dados personalizados que você configurar).  <br/> |Impedir que os usuários enviem arquivos rotulados como altamente confidenciais para fora da organização. Permitir que os usuários substituam isso fornecendo justificativa, incluindo com quem eles estão compartilhando o arquivo.  <br/> |
|Rótulos de confidencialidade  <br/> ||||Usar os Rótulos de confidencialidade para automaticamente criptografar e conceder permissões aos arquivos. Usar os Rótulos de confidencialidade para criptografar os arquivos. Essa proteção acompanha os arquivos caso eles sejam vazados.  <br/> O Office 365 não pode ler arquivos criptografados com a Proteção de Informações do Azure. Além disso, as políticas DLP podem funcionar apenas com os metadados (incluindo rótulos), mas não com o conteúdo desses arquivos (como números de cartão de crédito em arquivos).  <br/> |
   
Para obter as etapas para implantar os quatro tipos diferentes de sites de equipe do SharePoint Online nesta solução, consulte [Implantar sites do SharePoint Online para três níveis de proteção](../../compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection.md). 
  
## <a name="office-365-retention-labels"></a>Rótulos de retenção do Office 365

O uso dos rótulos de retenção é recomendado para ambientes com os dados confidenciais. Depois de configurar e publicar rótulos de retenção:
  
- Você pode aplicar um rótulo padrão a uma biblioteca de documentos em um site de equipe do SharePoint Online, de forma que todos os documentos nessa biblioteca recebam o rótulo padrão. 
    
- Você pode aplicar automaticamente rótulos ao conteúdo que corresponder a condições específicas.
    
- Você pode aplicar políticas DLP que se baseiem nos rótulos de retenção.
    
- Pessoas na sua organização podem aplicar manualmente um rótulo ao conteúdo no Outlook na Web, Outlook 2010 e posteriores, OneDrive for Business, SharePoint Online e grupos do Office 365. Os usuários geralmente sabem melhor o tipo de conteúdo com o qual estão trabalhando, portanto podem classificá-lo e aplicar a política DLP apropriada.
    
![Configuração recomendada para sites do SharePoint](../media/7fed0126-ab4a-4480-922c-681970642339.png)
  
Conforme ilustrado, essa solução inclui a criação dos seguintes rótulos de retenção:
  
- Altamente confidencial
    
- Confidencial
    
- Private
    
- Público interno
    
Esses rótulos são mapeados para os sites recomendados nas ilustrações e gráficos anteriormente neste artigo. Esta solução recomenda a configuração de políticas DLP para ajudar a evitar vazamento de arquivos rotulados como Confidenciais e Altamente Confidenciais.
  
Para as etapas de configuração de rótulos e políticas DLP de retenção nesta solução, consulte [Proteger os arquivos do SharePoint Online com rótulos de retenção e DLP](../../compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp.md).
  
## <a name="sensitivity-labels"></a>Rótulos de confidencialidade 

Se for necessário para o seu cenário de segurança, você pode usar rótulos de confidencialidade para aplicar proteções que acompanham os arquivos onde quer que estejam. Os Rótulos de Proteção de Informações do Azure e os Rótulos de confidencialidade no Centro de conformidade do Microsoft 365 são os mesmos. Para esta solução, recomendamos que você use uma política de Proteção de Informações do Azure e um sub-rótulo altamente confidencial para criptografar e conceder permissões a arquivos que precisam ser protegidos com o mais alto nível de segurança. 
  
Lembre-se de que quando a criptografia da Proteção de Informações do Azure é aplicada aos arquivos armazenados no Office 365, o serviço não pode processar o conteúdo desses arquivos. Coautoria, descoberta eletrônica, pesquisa, Delve e outros recursos de colaboração não funcionam. Políticas de DLP só funcionam com metadados (incluindo rótulos de retenção), mas não com o conteúdo desses arquivos (como números de cartão de crédito em arquivos).

Para saber mais, confira [Visão geral de rótulos de confidencialidade](../../compliance/sensitivity-labels.md).

    
### <a name="adding-permissions-for-external-users"></a>Adicionando permissões para usuários externos

Há duas maneiras para conceder aos usuários externos o acesso aos arquivos protegidos com a Proteção de Informações do Azure. Em ambos os casos, os usuários externos devem ter uma conta do Azure AD. Se os usuários externos não forem membros de uma organização que usa o Azure AD, eles poderão obter uma conta do Azure AD como um indivíduo usando essa página de entrada: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).
  
- Adicionar usuários externos a um grupo do Azure AD usado para configurar a proteção para um rótulo
    
     Primeiro você precisará adicionar a conta como um usuário de B2B em seu diretório. Pode levar algumas horas para o [cache de associação de grupo pelo Microsoft Azure AD Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare). Com esse método, as permissões são concedidas a todos os arquivos existentes protegidos com o rótulo (até mesmo a arquivos protegidos antes de um usuário ser adicionado ao grupo do Azure AD).
    
- Adicionar usuários externos diretamente à proteção de rótulo
    
     Você pode adicionar todos os usuários de uma organização (por exemplo, Fabrikam.com), um grupo do Azure AD (por exemplo, um grupo de finanças dentro de uma organização) ou um usuário individual. Por exemplo, você pode adicionar uma equipe externa de agências reguladoras à proteção para um rótulo. Com esse método, as permissões são concedidas apenas para arquivos protegidos com o rótulo depois que a entidade externa é adicionada à proteção.
    
### <a name="deploying-and-using-azure-information-protection"></a>Implantando e usando a Proteção de Informações do Azure

Para as etapas de configuração de Proteção de Informações do Azure nesta solução, consulte [Proteger arquivos do SharePoint Online com a Proteção de Informações do Azure](../../compliance/protect-sharepoint-online-files-with-azure-information-protection.md).
  

## <a name="next-step"></a>Próxima etapa

Crie isso como uma prova de conceito com [Proteger sites do SharePoint Online em um ambiente de desenvolvimento/teste](secure-sharepoint-online-sites-in-a-dev-test-environment.md).

## <a name="see-also"></a>Confira também

[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
