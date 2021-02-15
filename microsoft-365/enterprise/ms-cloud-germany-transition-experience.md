---
title: O que mudou para a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Resumo: Entenda o que mudou ao mudar do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região de datacenter alemã.'
ms.openlocfilehash: 0415f7b95cb9a9f2625798311946dac0f1f7c2c0
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688606"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>O que mudou para a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs

As migrações de locatários são projetadas para ter um efeito mínimo sobre administradores e usuários. No entanto, há considerações para cada carga de trabalho. Revise as seções a seguir para ter uma compreensão melhor da experiência de migração das cargas de trabalho.

A seguir estão as principais diferenças entre os serviços do Microsoft Cloud Deutschland e o Office 365 nas novas regiões de datacenter alemãs.

| Categoria | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | Serviços do Office 365 nas novas regiões de datacenter alemãs  |
|:-------|:-----|:-------|
| Serviços disponíveis do Microsoft 365 para assinatura com apenas um locatário do Office 365 | 15 serviços | 29 serviços <br><br> Para saber mais, confira Qual é a disponibilidade de serviço entre as diferentes ofertas de serviço de nuvem [do Office 365?](ms-cloud-germany-transition.md#serv-avail). |
| Novos recursos | Não há novos recursos disponíveis. | Os novos recursos estarão disponíveis de forma consistente com os serviços do Office 365. |
| Objeto de confiança dos dados | Sim | Não |
| Colaboração entre os locatários com locatários globais do Office 365 | Não | Sim |
| Residência de dados do cliente | Os dados do cliente serão armazenados exclusivamente em data centers alemães. | A Microsoft armazenará os seguintes Dados do cliente em repouso exclusivamente na Alemanha: <ul><li> Conteúdo da caixa de correio do Exchange Online (corpo do email, entradas de calendário e o conteúdo de anexos de email) </li><li> Conteúdo do site do SharePoint Online e os arquivos armazenados nesse site e arquivos carregados no OneDrive for Business </li></ul> |
| Termos aplicáveis | [Termos do Online Services](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) com este [suplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Termos dos Serviços Online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

O que não está mudando:

- O domínio inicial do locatário (como) com a ID de locatário `contoso.onmicrosoft.de` (GUID) e domínios personalizados persistirão após a migração. 

- As solicitações de autenticação para recursos migrados para os serviços do Office 365 são concedidas pelo serviço de autenticação do Azure dos serviços do Office 365 ( `login.microsoftonline.com` ). Durante a migração, os recursos que permanecem ainda no Office 365 Germany são autenticados pelo serviço Azure da Alemanha existente ( `login.microsoftonline.de` ).

Considerações a observar:

- Para contas de domínio gerenciado, após a cópia do locatário inicial do Azure Active Directory (Azure AD) está concluída (que é a primeira etapa da migração do Azure AD para o serviço do Azure AD dos serviços do Office 365), as alterações de senha, as alterações de senha de autoatendido (SSPR) e a redefinição de senha por administradores devem ser feitas nos portais de serviço do Office 365. As solicitações para atualizar senhas do serviço da Alemanha não serão bem-sucedidas neste ponto, porque o locatário do Azure AD foi migrado para os serviços do Office 365. As redefinições de senhas de domínio federado não são afetadas, pois são concluídas no diretório local.

- As entrada do Azure são apresentadas no portal onde o usuário tenta acessar. Os logs de auditoria estão disponíveis apenas no ponto de extremidade de serviços do Office 365 após a transição. Antes de migrar para a conclusão da migração, você deve salvar os logs de login e auditoria do portal do Microsoft Cloud Deutschland.

- As redefinições de senha, as alterações de senha, a redefinição de senha por um administrador de organizações gerenciadas (que não estão usando os Serviços de Federação do Active Directory) devem ser executadas por meio do portal de serviços do Office 365. As tentativas dos usuários que acessam os portais do Microsoft Cloud Deutschland para redefinir senhas falharão.

- As Solicitações de Assunto de Dados (DSRs) do Regulamento Geral sobre a Proteção de Dados (RGPD) são executadas a partir do portal de administração do Azure dos serviços do Office 365 para solicitações futuras. Todos os dados de diagnóstico herdados ou que não são do cliente residentes no Microsoft Cloud Deutschland são excluídos em ou antes de 30 dias.

## <a name="subscriptions--licenses"></a>Assinaturas & Licenças

- As assinaturas do Office 365 e do Dynamics do Microsoft Cloud Deutschland são transição para a região alemã com a realocação do Azure AD. Em seguida, a organização é atualizada para refletir novas assinaturas de serviços do Office 365. Durante o breve processo de transferência de assinatura, as alterações nas assinaturas são bloqueadas.

- À medida que o locatário é transições para os serviços do Office 365, suas assinaturas e licenças específicas da Alemanha são padronizadas com novas ofertas de serviços do Office 365. Assinaturas de serviços do Office 365 correspondentes são adquiridas para as assinaturas transferidas da Alemanha. Os usuários com licenças da Alemanha receberão licenças de serviços do Office 365. Após a conclusão, as assinaturas herdadas da Alemanha são canceladas e removidas do locatário de serviços atual do Office 365.

- Após a migração das cargas de trabalho individuais, funcionalidade adicional é disponibilizada por meio dos serviços do Office 365 (como Microsoft Planner e Microsoft Flow) devido às novas assinaturas de serviços do Office 365. Se apropriado para sua organização, o locatário ou administrador de licenciamento pode desabilitar novos planos de serviço conforme você planeja o gerenciamento de alterações para introduzir os novos serviços. Para obter orientação sobre como desabilitar planos de serviço atribuídos às licenças dos usuários, confira Desabilitar o acesso aos serviços do [Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)ao atribuir licenças de usuário.

## <a name="exchange-online"></a>Exchange Online

- As URLs de recursos do Exchange são migradas do ponto de extremidade herddo da Alemanha para o ponto de extremidade de serviços do `outlook.office.de` Office 365 `outlook.office365.com` após a migração. Os usuários podem acessar suas caixas de correio migradas usando a URL herdada até que a migração seja concluída. Os clientes devem fazer a transição dos usuários para a nova URL assim que possível após a migração do Exchange começar a evitar afetar a baixa do ambiente da Alemanha. As URLs de serviços do Office 365 para serviços do Outlook ficam disponíveis somente após o início da migração do Exchange.

- As caixas de correio são migradas como um processo de back-back. Os usuários em sua organização podem estar no Microsoft Cloud Deutschland ou na região alemã durante a transição e fazem parte da mesma organização do Exchange (na mesma lista de endereços global).

- Os usuários do Outlook Web App que acessam o serviço usando uma URL onde sua caixa de correio não reside verão um prompt de autenticação extra. Por exemplo, se a caixa de correio do usuário estiver nos serviços do Office 365 e a conexão do usuário com o Outlook Web App usar o ponto de extremidade herdado, o usuário irá autenticar primeiro e, em seguida, para `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` . Quando a migração for concluída, o usuário poderá acessar a nova URL ( ) e verá apenas a solicitação de entrada `https://outlook.office365.com` única e esperada. 

## <a name="office-services"></a>Serviços do Office

Os serviços do Office Online podem ser `office.de` acessados antes e durante a transição. Depois que as caixas de correio dos usuários são transição para os serviços do Office 365, os usuários devem começar a usar URLs de serviços do Office 365. À medida que as cargas de trabalho subsequentes migrarem para os serviços do Office 365, sua interface do portal do office.com começará a funcionar.

## <a name="exchange-online-protection"></a>Proteção do Exchange Online

- Os recursos do Exchange Online Protection (EOP) back-end são copiados para a nova região da Alemanha.
- Os usuários do Centro de Conformidade e Segurança do Office 365 precisam fazer a transição para usar URLs globais, como `https://protection.office.com` parte da migração.

## <a name="skype-for-business-online"></a>Skype for Business Online

Os clientes existentes do Skype for Business Online farão a transição para o Microsoft Teams. Para obter mais informações, consulte [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Vídeo do Office 365

O Vídeo do Office 365 será retirado em 1º de março de 2021 e o Vídeo do Office 365 não terá suporte após a conclusão da migração do SharePoint Online para as novas regiões de datacenter alemãs. O conteúdo do Vídeo do Office 365 será migrado como parte da migração do SharePoint Online. No entanto, os vídeos no Vídeo do Office 365 não reproduzirão na interface do usuário de vídeo do Office 365 após a migração do SharePoint. Saiba mais sobre a linha do tempo de migração na transição de vídeo do [Office 365 para o Microsoft Stream (clássico).](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Próxima etapa

[Compreender as ações e os impactos das fases de migração](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mais informações

Iniciando:

- [Migração do Microsoft Cloud Deutschland para os serviços do Office 365 nas novas regiões de datacenter alemãs](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)

Passando pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD](ms-cloud-germany-transition-azure-ad.md), [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos em nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
