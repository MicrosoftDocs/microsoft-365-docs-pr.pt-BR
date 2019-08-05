---
title: Solicitações de Entidades de Dados para o RGPD
description: ''
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: dc4352ac14f42a227f1572b0c7f1442aa4dec838
ms.sourcegitcommit: c201f5cc13d501e5207ebad166e42f90260af0c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2019
ms.locfileid: "35078901"
---
# <a name="data-subject-requests-and-the-gdpr"></a>Solicitações de Entidades de Dados para o RGPD

O RGPD introduz novas regras a empresas, agências governamentais, organizações sem fins lucrativos e outras organizações que ofereçam bens e serviços a pessoas na União Europeia (UE) ou que coletam e analisam dados vinculados a residentes na UE. O RGPD se aplica onde quer que você e sua empresa estejam localizados. É possível encontrar mais informações no [tópico Resumo RGDP](gdpr.md). <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWs1SI] 

Neste documento, você poderá obter informações sobre como concluir as notificações de violação no RGPD usando produtos e serviços da Microsoft.

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Família do Visual Studio](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Suporte e Serviços Profissionais da Microsoft](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>Terminologia

Definições úteis para os termos RGPD usados neste documento:

- *Controlador de dados (controlador*): uma pessoa jurídica, uma autoridade pública, uma agência ou outro corpo que, isoladamente ou em conjunto com outras pessoas, determina a finalidade e o meio de processamento de dados pessoais.  
- *Dados pessoais* e *entidade de dados*: qualquer informação relacionada a uma pessoa natural identificada ou identificável (entidade de dados); uma pessoa natural identificável é uma que pode ser identificada, direta ou indiretamente.  
- *Processador:* uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.  
- *Dados do cliente*: dados produzidos e armazenados nas operações do dia a dia para o trabalho em andamento.

## <a name="what-is-a-dsr"></a>O que é um DSR?

O RGPD (Regulamento Geral sobre a Proteção de Dados) da União Europeia concede o direito às pessoas (conhecidas na regulamentação como entidades de dados) de gerenciar os dados pessoais coletados por um empregador ou outro tipo de agência ou organização (conhecidos como controladores de dados ou apenas controladores). O RGPD fornece às entidades de dados direitos específicos a seus dados pessoais. Esses direitos incluem obter cópias, solicitar alterações, restringir o processamento, excluir ou receber os dados em um formato eletrônico para que eles possam ser passados para outro controlador.

Como um controlador você é obrigado a levar em consideração imediatamente cada DSR e fornecer uma resposta substantiva, basta executar a ação solicitada ou fornecer uma explicação sobre por que o DSR não pode ser acomodado pelo controlador. Um controlador deve consultar seus próprios consultores legais ou de conformidade quanto ao descarte apropriado de um determinado DSR.

Vários processos podem estar envolvidos em concluir um DSR, sujeito às regras de RGPD de conformidade da sua organização.
  
- **Descoberta**. O processo de determinar quais dados são necessários para concluir um DSR.
- **Acessar**. Recuperação e transmissão potencial para o assunto dos dados das informações descobertas.
- **Retificar**. Implemente alterações ou outros dados pessoais solicitados.
- **Restringir**. Alterar o acesso ou processamento de dados persona restringindo o acesso ou removendo dados da nuvem da Microsoft.
- **Exportar**. Fornecendo um formato "estruturado, comumente usado, de uso de máquina" de dados pessoais para o assunto de dados, conforme fornecido pela RGPD"direito da portabilidade de dados".
- **Excluir**. Remoção permanente de dados pessoais da nuvem da Microsoft.

## <a name="specific-dsr-considerations"></a>Considerações específicas sobre DSR

### <a name="insights-generated-by-microsoft-products-or-services"></a>Ideias geradas por produtos ou serviços da Microsoft

[As ideias](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) podem ser geradas por serviços (MyAnalytics, etc.) O Office 365 inclui serviços online que fornecem ideias para usuários e organizações que os utilizam. Os dados gerados por esses serviços podem produzir dados pessoais relevantes para um DSR. Siga o link na lista abaixo para obter detalhes sobre processos DSR específicos do serviço.  

### <a name="dsrs-for-system-generated-logs"></a>DSRs para logs gerados pelo sistema

Os logs e os dados relacionados gerados pela Microsoft podem conter dados pessoais considerados pessoais sob a definição RGPD de "dados pessoais". Não há suporte para a capacidade de restringir ou corrigir dados nos logs gerados pelo sistema. Dados em logs gerados pelo sistema constituem ações concretas realizadas na nuvem da Microsoft e dados de diagnóstico, e a modificação de tais dados comprometeria o registro histórico de ações e aumentaria os riscos de segurança e fraude. A Microsoft oferece a capacidade de acessar, exportar e excluir registros gerados pelo sistema que podem ser necessários para concluir um DSR. Alguns exemplos de dados podem incluir:  

- Dados de uso de produtos e serviços, como os log de atividades do usuário
- Dados de solicitações e consultas de pesquisa do usuário
- Dados gerados por produtos e serviços como resultado da funcionalidade do sistema e da interação de usuários ou de outros sistemas.  

### <a name="yammer-and-kaizala"></a>Yammer e Kaizala

Excluir uma conta de usuário não removerá logs geradas pelo sistema para o Yammer e Kaizala. Para remover os dados desses aplicativos, siga um destes procedimentos:

- [Gerenciar solicitações de entidades de dados do RGPD do Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [Exportar ou excluir dados organizacionais do usuário no Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>Nuvens nacionais

Em algumas nuvens nacionais, um administrador de TI global precisa excluir os logs gerados pelo sistema.

### <a name="microsoft-services"></a>Serviços da Microsoft

Se a sua organização ou os usuários se envolver com a Microsoft para receber o suporte, os produtos e serviços da Microsoft podem conter dados pessoais. Para saber mais informações, confira [Solicitações de titulares dos dados ao suporte e aos Serviços profissionais da Microsoft sobre o RGPD](gdpr-dsr-prof-services.md).

### <a name="microsoft-controller-products"></a>Produtos do Microsoft Controller

Em algumas circunstâncias, os usuários de sua organização podem acessar produtos ou serviços da Microsoft para os quais a Microsoft é o controlador de dados. Nesses casos, os usuários precisam iniciar seu próprio DSRs diretamente na Microsoft, e a Microsoft preenche as solicitações diretamente para o usuário.

### <a name="third-party-products"></a>Produtos de terceiros

Para produtos e serviços de terceiros acessados por meio da autenticação de conta da Microsoft, as solicitações de assunto de dados devem ser direcionadas para a terceira parte aplicável.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
