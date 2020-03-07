---
title: Notificação de falha
description: Como os serviços da Microsoft protegem contra uma violação de dados pessoais e como a Microsoft responderá e notificará você se ocorrer uma falha.
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 4cf6bb62034708b6ba21fb060949de6f1ac19066
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558081"
---
# <a name="gdpr-breach-notification"></a>Notificação de falha de RGPD

O RGPD introduz novas regras a empresas, agências governamentais, organizações sem fins lucrativos e outras organizações que ofereçam bens e serviços a pessoas na União Europeia (UE) ou que coletam e analisam dados vinculados a residentes na UE. O RGPD se aplica onde quer que você e sua empresa estejam localizados. É possível encontrar mais informações no [tópico Resumo do RGDP](gdpr.md). Neste documento, você poderá obter informações sobre como concluir as notificações de violação no RGPD, usando produtos e serviços da Microsoft.

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>O que constitui uma violação de dados pessoais no âmbito do RGPD?

Dados pessoais significam quaisquer informações relacionadas a um indivíduo que possam ser usadas para identificá-los direta ou indiretamente. Uma violação de dados pessoais é “uma violação de segurança que resulta em destruição acidental ou ilegal, perda, alteração, divulgação não autorizada ou acesso a dados pessoais transmitidos, armazenados ou processados”.

## <a name="terminology"></a>Terminologia

Definições úteis para os termos do RGPD usados neste documento:

- *Controlador de Dados (Controlador*): uma pessoa jurídica, uma autoridade pública, uma agência ou outro corpo que, isoladamente ou em conjunto com outras pessoas, determina a finalidade e o meio de processamento de dados pessoais.  
- *Dados pessoais* e *entidade de dados*: qualquer informação relacionada a uma pessoa natural identificada ou identificável (entidade de dados); uma pessoa natural identificável é uma que pode ser identificada, direta ou indiretamente.  
- *Processador:* uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.  
- *Dados do Cliente*: dados produzidos e armazenados nas operações do dia a dia para o trabalho em andamento.

## <a name="microsoft-and-breach-notification"></a>Notificação de violação e da Microsoft

A Microsoft leva a sério as suas obrigações de acordo com o RGPD (Regulamento Geral de Proteção de Dados). Uma violação de dados/incidente de segurança refere-se a eventos como acesso ilícito aos dados do cliente armazenados em equipamentos da Microsoft ou em instalações da Microsoft, ou acesso não autorizado a tal que tem o potencial de resultar na perda, revelação ou alteração dos dados do cliente.

Como um processador de dados, a Microsoft garante que os clientes do serviço possam atender aos requisitos de notificação de violação do RGPD como controladores de dados. Nossa notificação fornece as informações necessárias para a avaliação. A Microsoft informa aos clientes sobre qualquer falha de dados pessoais, exceto para os casos em que os dados pessoais sejam confirmados como ininteligíveis (por exemplo, dados criptografados com criptografia de integridade de teclas).

Os controladores de dados são responsáveis por avaliar os riscos de privacidade de dados e determinar se uma violação exige uma notificação do DPA do cliente. A Microsoft fornece as informações necessárias, juntamente com sua política de conformidade do RGPD, para fazer essa avaliação.

A notificação inicial inclui uma descrição da natureza da violação, o impacto aproximado do usuário e as etapas de mitigação (se aplicável). Caso a investigação não seja concluída no momento da notificação inicial, vamos indicar as próximas etapas e linhas do tempo para comunicações subsequentes. Para obter mais informações sobre como a Microsoft detecta e responde a uma violação de dados pessoais, confira [Notificação de violação de dados no RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) no Portal de Confiança do Serviço.

Os detalhes relacionados a notificações de violação para produtos e serviços específicos da Microsoft são fornecidos a seguir.
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    A Microsoft investe fortemente em sistemas, processos e equipes para reduzir a probabilidade de violação de dados pessoais e para rapidamente detectar e reduzir a consequência da violação, caso ocorra. Mais detalhes podem ser lidos em [Investimentos do Office 365 na segurança de dados](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).

    Um cliente pode ficar atento a uma violação e entrar em contato com a Microsoft. Nesse caso, notifique o Suporte da Microsoft, que criará uma interface com as equipes de engenharia para obter mais informações.

2. **[Azure & Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    A Microsoft tem um serviço global de respostas 24 horas por dia, que funciona para reduzir os efeitos de ataques no Microsoft Azure e no Dynamics 365.

    - *Detecção de Violações*: Como a Microsoft e o cliente têm obrigações de segurança, os serviços do Azure usam um modelo de responsabilidade compartilhada para definir responsabilidades de segurança e operacionais. A Microsoft não monitora ou responde a incidentes de segurança no domínio de responsabilidade do cliente. A resposta a incidentes de clientes pode envolver a colaboração [com o suporte ao cliente](https://azure.microsoft.com/support/options/) do Azure, dados os contratos de serviço apropriados. O Microsoft Azure também oferece vários serviços (por exemplo, a [Central de Segurança do Azure](https://azure.microsoft.com/services/security-center/)) que os clientes podem usar para desenvolver e gerenciar respostas a incidentes de segurança.

        Para obter uma lista de eventos que disparam uma investigação de violação no Microsoft Azure, confira [Detecção de possíveis violações](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches). [O Azure e a Notificação de Violação no âmbito do RGPD](gdpr-breach-azure-dynamics.md) fornecem detalhes adicionais sobre como a Microsoft investiga, gerencia e responde a incidentes de segurança no Azure.

    - *Resposta à Violação de Dados*: a Microsoft determina a prioridade adequada e os níveis de gravidade de uma violação analisando o impacto funcional, a capacidade de recuperação e o impacto das informações do incidente. A prioridade e a severidade podem mudar durante a investigação, com base nas novas descobertas e conclusões.
    A equipe de resposta de segurança da Microsoft trabalha em conjunto com consultores jurídicos globais para ajudar a garantir que as perícias sejam realizadas de acordo com obrigações legais e compromissos com os clientes. Esses processos estão detalhados na [Resposta de Violação de Dados do Azure](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).

    - *Notificação de Cliente*: o Microsoft Azure notifica os clientes e as autoridades normativas das violações de dados conforme necessário. As notificações dos clientes são oferecidas em não mais de 72 horas a partir do prazo, com exceção das seguintes circunstâncias:

        - A Microsoft acredita que o ato de executar uma notificação aumentará o risco para outros clientes.
        - O cronograma de 72 horas pode deixar alguns detalhes do incidente disponíveis. Estes detalhes serão fornecidos para você à medida que a investigação prosseguir.

        Mais detalhes podem ser encontrados na [Notificação do Cliente](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification).

3. **[Suporte e Serviços Profissionais da Microsoft](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    A natureza dos serviços profissionais significa que alguns incidentes de proteção de dados podem se enquadrar no domínio de responsabilidade do cliente. Quando o Microsoft Professional Services identifica um incidente de proteção de dados, ele acompanha o plano de resposta padrão do setor, conforme descrito em [Escopo e limites do processo de resposta a incidentes de proteção de dados](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).

## <a name="breach-notification-admin-tools"></a>Ferramentas administrativas de notificação de violação

- **Defina os contatos de privacidade da sua organização**: os administradores de locatários podem usar o [Portal de Administração do Active Directory](https://go.microsoft.com/fwlink/p/?linkid=2052736) para definir o contato de privacidade da organização caso precise se comunicar com eles.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
