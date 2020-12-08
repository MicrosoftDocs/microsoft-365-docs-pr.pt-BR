---
title: Privacidade e dados pessoais
description: Detalha os dados coletados, armazenados e usados pelo serviço
keywords: RGPD, retenção, exclusão, armazenamento, retenção, processamento, segurança, auditoria
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 8412c10416a4a131129eebd20d1b4f01228afaf3
ms.sourcegitcommit: 280200281aec862517876319a3fe4ce170674047
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586680"
---
# <a name="privacy-and-personal-data"></a>Privacidade e dados pessoais

Os usuários podem receber, transmitir e armazenar dados em dispositivos gerenciados pela área de trabalho gerenciada da Microsoft. Eles confiam que a privacidade dos dados está protegida e usada apenas de uma maneira consistente com suas expectativas. Este artigo explica como a área de trabalho gerenciada da Microsoft coleta, armazena, mantém, processa, protege, compartilha, audita e exporta dados pessoais. Você também aprenderá como um administrador pode exibir, corrigir e excluir dados pessoais.

A área de trabalho gerenciada da Microsoft não usa dados pessoais coletados como parte de fornecer o serviço para fins de criação de perfil, propaganda ou marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Coleta de dados da área de trabalho gerenciada da Microsoft

Quando os usuários registram dispositivos corporativos na área de trabalho gerenciada da Microsoft, a coleta de dados é tratada – na camada técnica – usando o Windows e o Microsoft Intune. Essas fontes coletam dados pessoais sobre dispositivos de usuários, como nomes de dispositivos para a área de trabalho gerenciada da Microsoft, a fim de identificar o dispositivo a ser gerenciado e fornecido com as experiências da área de trabalho gerenciada da Microsoft.

O Microsoft Managed desktop não coleta dados sozinho para fornecer seu serviço (exceto para [informações de contato do administrador de ti](#it-admin-contact-information). Em vez disso, a área de trabalho gerenciada da Microsoft reutiliza dados que outras fontes, como o Windows e o Microsoft Intune, já foram coletadas. O Microsoft Managed desktop usa dados que esses serviços coletam de dispositivos registrados:

- Os dados de diagnóstico do Windows de dispositivos gerenciados pelo Microsoft Managed desktop são enviados para armazenamentos de dados de diagnóstico do Windows da Microsoft.
- O Microsoft Managed desktop usa o [Gerenciamento moderno](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) para gerenciar os dispositivos registrados. Como parte desse, os dispositivos devem ser registrados no Azure Active Directory do locatário.
- Para distribuir sua configuração altamente otimizada e segura para dispositivos registrados, o Microsoft Managed desktop usa o Microsoft Intune.
- O Microsoft Managed desktop usa dados de inteligência de segurança do Microsoft defender Advanced thread Protection para os clientes que usam esse serviço.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Armazenamento de dados e fontes na área de trabalho gerenciada da Microsoft

Após a área de trabalho gerenciada da Microsoft obter os dados, é necessário fornecer o serviço, o armazenamento e o processamento desses dados da seguinte maneira:

### <a name="storing-data-storage-location-and-data-retention"></a>Armazenamento de dados, local de armazenamento e retenção de dados

O Microsoft Managed desktop armazena seus dados em um ou mais dos seguintes serviços de armazenamento da Microsoft:

- Azure SQL
- Armazenamento do Azure

A área de trabalho gerenciada da Microsoft armazena seus dados nos Estados Unidos. Os dados pessoais são mantidos pela área de trabalho gerenciada da Microsoft por um máximo de 30 dias.

### <a name="staff-location"></a>Local da equipe

As equipes de operações de segurança do MMD e do MMD estão localizadas nos Estados Unidos e na Índia.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Uso de dados da área de trabalho gerenciada da Microsoft

O Microsoft Managed desktop usa estes dados:


| Fontes de dados |Usar com a área de trabalho gerenciada da Microsoft  |
|---------|---------|
|Dados do Azure Active Directory     | Usado em relatórios criados para administradores de locatários, que estão disponíveis no portal de administração de área de trabalho gerenciada da Microsoft.        |
|Dados do Intune     | Usado em relatórios criados para administradores de locatários, que estão disponíveis no portal de administração de área de trabalho gerenciada da Microsoft.        |
|Microsoft Defender para Ponto de Extremidade     |  Usado para lidar com ameaças de segurança detectadas em dispositivos registrados pelo centro de operações de segurança (SOC) da área de trabalho gerenciada da Microsoft.  |
|Dados de diagnóstico do Windows     |Usada para determinar o status de atualização de dispositivos gerenciados, bem como para fornecer e aprimorar a oferta de ti de serviço (ITaaS) do Microsoft Managed desktop.         |
|Dados de contato do administrador     | Usado pela área de trabalho gerenciada da Microsoft para se comunicar com administradores de locatários.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entidades processadas pela área de trabalho gerenciada da Microsoft

A área de trabalho gerenciada da Microsoft processa essas entidades para fornecer o serviço:

- Dados do dispositivo
- Configurações de segurança de dispositivo
- Sistema operacional e hardware do dispositivo
- Informações agregadas sobre a integridade do dispositivo
- Informações de diagnóstico do dispositivo
- Dados do locatário
- Recursos do Azure Active Directory
- Dados de política e configuração
- Metadados do Microsoft defender para ponto de extremidade
- Dados de diagnóstico do Windows
- Dados de uso de produtos e serviços

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Os dados de identidade usados pela área de trabalho gerenciada da Microsoft são armazenados pelo Active Directory do Azure em um local geográfico com base no endereço fornecido pela organização ao se inscrever em um serviço do Microsoft Online, como o Office 365 ou o Azure. Confira o [Microsoft Azure — onde estão os dados do meu cliente?](http://azuredatacentermap.azurewebsites.net/) para um mapa mostrando os datacenters do Azure Active Directory.

Para obter mais informações sobre as regiões que o Azure usa para armazenamento de dados, consulte [Azure Active Directory – onde seus dados estão localizados](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

Os dados do Intune podem ser armazenados em algumas regiões diferentes, como Europa (Irlanda) e Europa Ocidental (Países Baixos). O administrador de ti cria uma conta de locatário e escolhe o país onde os dados serão armazenados quando eles se inscreverem inicialmente nos serviços do Intune. Para obter uma lista de locais de datacenter usados pelo Intune, consulte [Microsoft Intune: onde estão os dados do meu cliente?](http://intunedatacentermap.azurewebsites.net/). Para obter mais informações sobre o armazenamento de dados e uso pelo Intune, confira [coleta de dados no Intune](https://docs.microsoft.com/intune/privacy-data-collect).

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para Ponto de Extremidade

Os dados do Microsoft defender para pontos de extremidade podem ser armazenados em algumas regiões diferentes. Por esse motivo, o defender para ponto de extremidade opera nos datacenters do Microsoft Azure na União Européia, no Reino Unido e nos Estados Unidos, conforme mencionado no [Microsoft defender para ponto de extremidade — locais de armazenamento de dados](http://intunedatacentermap.azurewebsites.net/). Para obter mais informações sobre o armazenamento de dados e uso pelo defender para ponto de extremidade, consulte [que dados o Microsoft defender para o ponto de extremidade coleta?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Conforme mencionado na [declaração de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement), "os dados pessoais coletados pela Microsoft podem ser armazenados e processados na sua região, nos Estados Unidos, e em qualquer outro país onde a Microsoft ou seus afiliados, subsidiárias ou provedores de serviços operem. [...] Normalmente, o local de armazenamento principal está na região do cliente ou nos Estados Unidos, geralmente com um backup para um datacenter em outra região. Os locais de armazenamento são escolhidos para operar com eficiência, para melhorar o desempenho e para criar redundâncias a fim de proteger os dados se houver uma falha ou outro problema. Seguimos as etapas para garantir que os dados que coletamos nesta política de privacidade sejam processados de acordo com as disposições desta declaração e os requisitos da legislação aplicável onde quer que os dados estejam localizados. "

Para obter mais informações sobre a coleta de dados de diagnóstico do Windows 10, consulte a seção ["onde armazenamos e processamos dados pessoais"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) da política de privacidade da Microsoft.

## <a name="data-access-protection"></a>Proteção de acesso a dados

O acesso direto aos armazenamentos de dados internos do Microsoft Managed desktop é restrito de várias maneiras:

- Requer aprovação de nível de líder da engenharia.
- É auditado e limitado por tempo.
- Ele exige o uso de uma estação de trabalho altamente segura e restrita.
- Todos os dados são criptografados enquanto são armazenados.
- Não há acesso à posição.
- O acesso ao portal de gerenciamento interno do Microsoft Managed desktop requer uma estação de trabalho altamente segura e restrita.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Processamento de dados pessoais de forma compatível
O Microsoft Managed desktop processa dados pessoais com sistemas certificados por ISO. Para obter mais informações, consulte [conformidade](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Criação de perfil e marketing

A área de trabalho gerenciada da Microsoft não usa dados pessoais coletados como parte de fornecer o serviço para fins de criação de perfil, propaganda ou marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de assunto de dados para o RGPD e o CCPA

O [rgpd (regulamentação geral de proteção de dados)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) da União Européia oferece direitos às pessoas (conhecidos na regulamentação como assuntos de dados) para gerenciar os dados pessoais que foram coletados por um empregador ou outro tipo de agência ou organização (conhecido como controlador de dados ou simplesmente controlador). Os dados pessoais são definidos em linhas gerais no GDPR como todos os dados relacionados a uma pessoa física identificada ou identificável. O GDPR fornece às entidades de dados direitos específicos a seus dados pessoais. Esses direitos incluem obter cópias, solicitar alterações, restringir o processamento, excluir ou receber os dados em um formato eletrônico para que eles possam ser passados para outro controlador. Uma solicitação formal feita por uma entidade de dados a um controlador para executar uma ação em seus dados pessoais é chamada neste documento de Solicitação de Direitos da Entidade de Dados  ou DSR.

Da mesma forma, a Califórnia Consumer Privacy Act (CCPA) oferece direitos de privacidade e obrigações para os clientes da Califórnia, incluindo direitos semelhantes aos direitos de assunto de dados do RGPD, como o direito de excluir, acessar e receber (portabilidade) suas informações pessoais. O CCPA também oferece algumas divulgações, proteções contra discriminação ao eleger os direitos de exercício e os requisitos de "recusa/aceitação" para determinadas transferências de dados classificadas como "vendas". As vendas são amplamente definidas para incluir o compartilhamento de dados para uma consideração valiosa. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

A seção a seguir descreve como a área de trabalho gerenciada da Microsoft ajuda os controladores a localizar, acessar e agir sobre dados pessoais ou informações pessoais usadas pelo Microsoft Managed desktop.

> [!NOTE]
> Se você estiver procurando informações gerais sobre o RGPD, consulte a [seção rgpd](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) do portal de confiança do serviço.

### <a name="it-admin-contact-information"></a>Informações de contato de administrador de ti

Um administrador de locatários pode exibir, corrigir e excluir seus próprios dados pessoais (como suas próprias informações de contato) diretamente na seção de contato de administrador do portal de área de trabalho gerenciada da Microsoft.

### <a name="user-related-personal-data"></a>Dados pessoais relacionados ao usuário

Além disso, a área de trabalho gerenciada da Microsoft não coleta dados pessoais por conta própria. Em vez disso, ele se baseia e usa dados pessoais que outros serviços do Microsoft Enterprise online coletados. Os administradores de ti que procuram responder às solicitações de usuário para exibir, corrigir e excluir seus dados pessoais podem usar a respectiva funcionalidade dos serviços subjacentes dos quais o Microsoft Managed desktop depende. Se você estiver interessado em exibir ou excluir dados pessoais usados por esses serviços, confira primeiro as [solicitações de entidades de dados do Azure para o artigo rgpd](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) .

Além disso, use as orientações a seguir para exercitar o DSRs para os serviços que a Microsoft Managed desktop depende para o conjunto de dados pessoais:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft defender para ponto de extremidade](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
