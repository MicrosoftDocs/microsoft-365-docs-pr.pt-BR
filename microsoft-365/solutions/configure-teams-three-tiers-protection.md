---
title: Configurar o Teams com três camadas de segurança para compartilhamento de arquivos
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- Ent_Architecture
- seo-marvel-jun2020
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
recommendations: false
description: Saiba como configurar o Teams para melhorar a segurança de compartilhamento de arquivos usando três camadas de proteção, equilibrando a segurança com a facilidade de colaboração.
ms.openlocfilehash: 34351b202575302e2929db48d7807b91e4308905
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683398"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>Configurar equipes com três camadas de proteção

Os artigos nesta série fornecem recomendações para configurar equipes no Microsoft Teams e seus sites do Microsoft Office SharePoint Online associados, para obter uma proteção de arquivos que equilibre segurança com facilidade de colaboração.

Este artigo define quatro configurações diferentes, começando com uma equipe pública com as políticas de compartilhamento mais abertas. Cada configuração adicional representa uma etapa significativa na proteção, enquanto a capacidade de acessar e colaborar em arquivos armazenados dentro de equipes é reduzida para o conjunto relevante de membros da equipe. 

As configurações nesse artigo se alinham às recomendações da Microsoft para três níveis de proteção de dados, identidades e dispositivos:

- Proteção de linha de base

- proteção confidencial

- Proteção altamente confidencial

Para obter mais informações sobre os níveis e as capacidades recomendadas para cada nível, consulte [Ilustrações do Microsoft Cloud for Enterprise Architects](./cloud-architecture-models.md)


## <a name="three-tiers-at-a-glance"></a>Visão rápida de três camadas

A tabela a seguir resume as configurações de cada camada. Use estas configurações como recomendações de ponto de partida e ajuste as configurações para atender às necessidades da sua organização. Você pode não precisar de todas as camadas.

|-|Linha de base (Público)|Linha de base (Particular)|Confidencial|Altamente confidencial|
|:-----|:-----|:-----|:-----|:-----|
|Equipe privada ou pública|Público|Private|Private|Private|
|Quem tem acesso?|Todas as pessoas na organização, incluindo usuários B2B.|Somente membros da equipe. Outras pessoas podem solicitar acesso ao site associado.|Somente membros da equipe.|Somente membros da equipe.|
|Canais privados|Proprietários e membros podem criar canais privados|Proprietários e membros podem criar canais privados|Somente proprietários podem criar canais privados|Somente proprietários podem criar canais privados|
|Acesso de convidado no nível do site|**Convidados novos e existentes** (padrão).|**Convidados novos e existentes** (padrão).|**Convidados novos e existentes** ou **Somente pessoas da sua organização**, dependendo das necessidades da equipe.|**Convidados novos e existentes** ou **Somente pessoas da sua organização**, dependendo das necessidades da equipe.|
|Configurações de compartilhamento de site|**Proprietários e membros do site e pessoas com permissões de edição podem compartilhar arquivos e pastas, mas apenas os proprietários do site podem compartilhar o site**.|**Proprietários e membros do site e pessoas com permissões de edição podem compartilhar arquivos e pastas, mas apenas os proprietários do site podem compartilhar o site**.|**Proprietários e membros do site e pessoas com permissões de edição podem compartilhar arquivos e pastas, mas apenas os proprietários do site podem compartilhar o site**.|**Somente os proprietários do site podem compartilhar arquivos, pastas e o site**.<br>Solicitações de acesso **Desativadas**.|
|Acesso a dispositivos não gerenciados no nível do site|**Acesso total a partir de aplicativos da área de trabalho, aplicativos móveis e da Web** (padrão).|**Acesso total a partir de aplicativos da área de trabalho, aplicativos móveis e da Web** (padrão).|**Permitir acesso limitado, somente na Web**.|**Bloquear acesso**.|
|Tipo de link de compartilhamento padrão|**Somente pessoas da sua organização**|**Somente pessoas da sua organização**|**Pessoas específicas**|**Pessoas com acesso existente**|
|Rótulos de confidencialidade|Nenhum|Nenhum|Rótulo de confidencialidade usado para classificar a equipe e controlar o compartilhamento de convidados e o acesso de dispositivos não gerenciados.|Rótulo de confidencialidade usado para classificar a equipe e controlar o compartilhamento de convidados e o acesso de dispositivos não gerenciados. O rótulo também pode ser usado em arquivos para criptografar arquivos.|

A opção [Equipes com isolamento de segurança](secure-teams-security-isolation.md), uma variação da opção altamente confidencial, usa um rótulo de confidencialidade exclusivo para uma equipe, o que proporciona mais segurança. Você pode usar este rótulo para criptografar arquivos, e somente membros dessa equipe poderão lê-los.

A proteção da linha de base inclui equipes públicas e privadas. As equipes públicas podem ser descobertas e acessadas por qualquer pessoa na organização. As equipes privadas podem ser descobertas e acessadas apenas por membros da equipe. Ambas as configurações restringem aos proprietários da equipe o compartilhamento do site do Microsoft Office SharePoint Online associado, para ajudar no gerenciamento de permissões.

As equipes de proteção confidencial e altamente confidencial são equipes privadas, nas quais o compartilhamento e a solicitação de acesso ao site associado são limitados e os rótulos de confidencialidade são usados para definir políticas de compartilhamento de convidados, acesso de dispositivos e criptografia de conteúdo.

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

As camadas confidencial e altamente confidencial usam rótulos de confidencialidade para ajudar a proteger a equipe e seus arquivos. Para implementar estas camadas, você deve habilitar os [rótulos de confidencialidade para proteger o conteúdo no Microsoft Teams, grupos do Office 365 e sites do Microsoft Office SharePoint Online](../compliance/sensitivity-labels-teams-groups-sites.md).

Embora a camada de linha de base não exija rótulos de confidencialidade, considere criar um rótulo "geral" e exigir que todas as equipes sejam rotuladas. Isso ajudará a garantir que os usuários façam uma escolha consciente em relação à confidencialidade ao criar uma equipe. Se você planeja implantar as camadas confidencial ou altamente confidencial, recomendamos a criação de um rótulo "geral" que você pode usar para equipes de linha de base e para arquivos que não são confidenciais.

Se você não conhece os rótulos de confidencialidade, recomendamos a leitura do artigo [Introdução aos rótulos de confidencialidade](../compliance/get-started-with-sensitivity-labels.md). 

Se você já implementou rótulos de confidencialidade em sua organização, considere como os rótulos usados nas camadas confidencial e altamente confidencial se ajustam à sua estratégia geral de rotulação. 

## <a name="sharing-the-sharepoint-site"></a>Compartilhar o site do Microsoft Office SharePoint Online

Cada equipe tem um site do Microsoft Office SharePoint Online associado, onde os documentos são armazenados. (Isso corresponde à guia **Arquivos** em um canal de equipe.) O site do Microsoft Office SharePoint Online mantém seu próprio gerenciamento de permissões, mas está vinculado às permissões de equipe. Os proprietários da equipe estão inclusos como proprietários de sites, e os membros da equipe estão incluídos como membros do site no site associado.

As permissões resultantes permitem:

- Que os proprietários da equipe administrem o site e tenham controle total sobre o conteúdo do site.
- Que os membros da equipe criem e editem arquivos no site. 

Por padrão, os proprietários e membros da equipe podem compartilhar o próprio site com pessoas de fora da equipe sem realmente adicioná-las à equipe. Não recomendamos isso, pois complica o gerenciamento de usuários e pode levar as pessoas que não são membros da equipe a terem acesso aos arquivos da equipe sem que os proprietários percebam. Para ajudar a evitar isso, começando no nível de proteção de linha de base, recomendamos que apenas os proprietários possam compartilhar o site diretamente.

Embora as equipes não tenham uma opção de permissão somente leitura, o site do Microsoft Office SharePoint Online possui. Se você possui participantes de grupos de parceiros que precisam poder exibir os arquivos da equipe, mas não editá-los, considere adicioná-los diretamente ao site do Microsoft Office SharePoint Online com permissões de Leitura.

## <a name="sharing-files-and-folders"></a>Compartilhar arquivos e pastas

Por padrão, proprietários e membros da equipe podem compartilhar arquivos e pastas com pessoas de fora da equipe. Isso pode incluir pessoas de fora da sua organização, se você tiver permitido o compartilhamento de convidados. Em todas as três camadas, atualizamos o tipo de link de compartilhamento padrão para ajudar a evitar o compartilhamento excessivo acidental. No nível altamente confidencial, restringimos esse compartilhamento apenas aos proprietários da equipe.

## <a name="guest-sharing"></a>Compartilhamento de convidados

Se você precisar colaborar com pessoas de fora da sua organização, recomendamos configurar a [integração do Microsoft Office SharePoint Online e OneDrive com o Microsoft Azure Active Directory B2B](/sharepoint/sharepoint-azureb2b-integration-preview) para obter a melhor experiência de compartilhamento e administração.

O compartilhamento de convidados de Equipes está desativado por padrão, embora o compartilhamento para grupos do Office 365 (onde a associação da equipe é armazenada) e o Microsoft Office SharePoint Online estejam ativados. Ativamos o compartilhamento de Equipes na camada de linha de base e você pode desativá-lo, se necessário, nas camadas confidencial e altamente confidencial, usando um rótulo de confidencialidade.

O rótulo de confidencialidade afeta apenas o compartilhamento de convidados da equipe. As configurações de compartilhamento de convidados para o site do Microsoft Office SharePoint Online associado são controladas separadamente, e você deve alinhar as duas configurações para as camadas confidencial e altamente confidencial.

Na camada altamente confidencial, configuramos o rótulo de confidencialidade para criptografar arquivos aos quais ele é aplicado. Se você precisar que os convidados tenham acesso a estes arquivos, deverá conceder permissões a eles ao criar o rótulo.

É altamente recomendável que você deixe o compartilhamento de convidados ativado para a camada de linha de base e para as camadas confidencial ou altamente confidencial se precisar colaborar com pessoas de fora da organização. Os recursos de compartilhamento de convidados no Microsoft 365 fornecem uma experiência de compartilhamento muito mais segura e controlável do que o envio de arquivos como anexos em mensagens de email. Também reduz o risco de TI sombra, em que os usuários usam produtos de consumo não controlados para compartilhar com colaboradores externos legítimos.

Confira as seguintes referências para criar um ambiente de compartilhamento de convidados seguro e produtivo para a sua organização:

- [Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)
- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](share-limit-accidental-exposure.md)
- [Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>Acesso de dispositivos não gerenciados

Para as camadas confidencial e altamente confidencial, restringimos o acesso ao conteúdo do Microsoft Office SharePoint Online com rótulos de confidencialidade. O acesso condicional do Azure AD oferece muitas opções para determinar como as pessoas acessam o Microsoft 365, incluindo limitações com base em localização, risco, conformidade do dispositivo e outros fatores. Recomendamos que você leia [O que é o Acesso Condicional?](/azure/active-directory/conditional-access/overview) e considere quais políticas adicionais podem ser apropriadas para sua organização.

Observe que os convidados geralmente não têm dispositivos gerenciados pela sua organização. Se você permitir aos convidados em qualquer uma das camadas, considere que tipos de dispositivos eles estarão usando para acessar equipes e sites e defina suas políticas de dispositivos não gerenciados de acordo.

### <a name="control-device-access-across-microsoft-365"></a>Controlar o acesso do dispositivo no Microsoft 365

A configuração de dispositivos não gerenciados nos rótulos de sensibilidade afeta somente o acesso do Microsoft Office SharePoint Online. Se quiser expandir o controle de dispositivos não gerenciados além do Microsoft Office SharePoint Online[, você poderá criar uma política de acesso condicional do Azure Active Directory para todos os aplicativos e serviços da sua organização](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) em vez disso. Para configurar essa política especificamente para [serviços do Microsoft 365](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#office-365), selecione o aplicativo de nuvem do **Office 365** em **Aplicativos ou ações do**.

![Captura de tela do aplicativo de nuvem do Office 365 em uma política de acesso condicional do Azure Active Directory](https://docs.microsoft.com/sharepoint/sharepointonline/media/azure-ca-office365-policy.png)

O uso de uma política que afete todos os serviços do Microsoft 365 pode levar a uma melhor segurança e uma melhor experiência para os usuários. Por exemplo, quando você bloqueia o acesso a dispositivos não gerenciados apenas no Microsoft Office SharePoint Online, os usuários podem acessar o chat em uma equipe com um dispositivo não gerenciado, mas perderão o acesso quando tentarem acessar a guia **Arquivos**. Usar o aplicativo de nuvem do Office 365 ajuda a evitar problemas com [dependências de serviço](/azure/active-directory/conditional-access/service-dependencies).

## <a name="next-step"></a>Próxima etapa

Comece [configurando o nível de linha de base de proteção](configure-teams-baseline-protection.md). Se necessário, você pode adicionar [proteção confidencial](configure-teams-sensitive-protection.md) e [altamente confidencial](configure-teams-highly-sensitive-protection.md) sobre a linha de base.

## <a name="see-also"></a>Confira também

[Segurança e conformidade no Microsoft Teams](/microsoftteams/security-compliance-overview)

[Políticas de alerta no centro de conformidade e segurança](../compliance/alert-policies.md)
