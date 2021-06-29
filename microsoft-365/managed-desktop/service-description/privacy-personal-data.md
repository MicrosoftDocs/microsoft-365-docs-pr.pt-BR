---
title: Privacidade e dados pessoais
description: Detalha os dados coletados, armazenados e usados pelo serviço
keywords: RGPD, retenção, exclusão, armazenamento, retenção, processamento, segurança, auditoria
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 453c26afd176a1282e466a73992ae4abe1542d68
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177472"
---
# <a name="overview"></a>Visão Geral

Área de Trabalho Gerenciada da Microsoft é um serviço ITaaS (it-as-service) para clientes de nuvem empresarial projetado para manter os dispositivos de Windows dos funcionários implantados e atualizados. Ele também fornece operações e gerenciamento de serviços de IT, monitora a resposta a incidentes e segurança, além de fornecer suporte ao usuário. Esta documentação fornece detalhes adicionais sobre a plataforma de dados e a conformidade de privacidade para Área de Trabalho Gerenciada da Microsoft.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Área de Trabalho Gerenciada da Microsoft fontes de dados e finalidade

Área de Trabalho Gerenciada da Microsoft fornece seu serviço aos clientes corporativos e administra corretamente os dispositivos inscritos dos clientes usando dados de várias fontes. Essas fontes, incluindo Azure Active Directory, Microsoft Intune, Microsoft Windows 10 e Microsoft Defender para Ponto de Extremidade, fornecem uma visão abrangente dos dispositivos que Área de Trabalho Gerenciada da Microsoft gerencia. O serviço também usa essas serviços Microsoft para habilitar Área de Trabalho Gerenciada da Microsoft fornecer recursos ITaaS:

- [Microsoft Windows 10 Enterprise](/windows/windows-10/) - para gerenciamento da experiência de configuração de dispositivo, gerenciamento de conexões com outros serviços e suporte operacional para profissionais de IT.
- [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) - usa Windows 10 Enterprise dados de diagnóstico para fornecer informações adicionais sobre Windows 10 atualização. 
- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) – para gerenciamento de dispositivos e para manter seus dados seguros.
  - [Microsoft Azure Active Directory](/azure/active-directory/) - para autenticação e identificação de todas as contas de usuário. 
  - [Microsoft Intune](/mem/intune/) – para distribuir configurações de dispositivo, gerenciamento de dispositivos e gerenciamento de aplicativos.
  - [Análise de ponto de](/mem/analytics/overview) extremidade – para informações analíticas sobre o uso de dispositivos e aplicativos.
  - [Windows Autopilot](/microsoft-365/windows/windows-autopilot) – para provisionamento e implantação de dispositivos.
  - [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/) – fornece serviços de segurança, como monitoramento de segurança de dispositivos e dados de inteligência de segurança.
- [Área de Trabalho Gerenciada da Microsoft](https://endpoint.microsoft.com/#home) – Dados fornecidos pelo cliente ou gerados pelo serviço durante a execução do serviço.
- [Microsoft 365 aplicativos para empresas](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) – para gerenciamento de Microsoft 365 Apps.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Área de Trabalho Gerenciada da Microsoft de dados e armazenamento

Área de Trabalho Gerenciada da Microsoft conta com dados de vários produtos e serviços da Microsoft para fornecer seu serviço aos clientes corporativos. Para atingir o objetivo de proteger e manter dispositivos inscritos, processemos e copiamos dados desses serviços para Área de Trabalho Gerenciada da Microsoft. Ao processar dados, seguiremos as instruções documentadas fornecidas por você, conforme referenciado nos Termos de Serviços Online e Na Declaração de Privacidade da Microsoft. Ao processar dados, seguiremos as instruções documentadas fornecidas por você, conforme referenciado nos Termos de Serviços [Online](https://www.microsoft.com/licensing/product-licensing/products) e Na [Declaração de Privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement) Área de Trabalho Gerenciada da Microsoft tarefas do processador incluem garantir a confidencialidade, a segurança e a resiliência apropriadas. Área de Trabalho Gerenciada da Microsoft emprega medidas adicionais de privacidade e segurança para garantir o tratamento adequado de dados de identificação pessoal. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Área de Trabalho Gerenciada da Microsoft armazenamento de dados e local da equipe

Área de Trabalho Gerenciada da Microsoft armazena seus dados nos data centers do Azure nos Estados Unidos. Os dados pessoais obtidos pela Área de Trabalho Gerenciada da Microsoft e outros serviços são necessários para manter o serviço operacional. Se um dispositivo for removido do Área de Trabalho Gerenciada da Microsoft, manteremos dados pessoais por no máximo 30 dias, exceto para dados de alerta coletados pelo Microsoft Defender para Ponto de Extremidade, que são armazenados por 180 dias para fins de segurança. Para obter mais informações sobre retenção de dados, consulte [Retenção de dados, exclusão](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)e destruição em Microsoft 365 .

Área de Trabalho Gerenciada da Microsoft As equipes de Operações de Engenharia e Operações de Segurança estão localizadas nos Estados Unidos e na Índia. 

## <a name="microsoft-windows-10-diagnostic-data"></a>Dados Windows 10 de diagnóstico da Microsoft

Área de Trabalho Gerenciada da Microsoft usa [Windows 10 dados](/windows/privacy/windows-diagnostic-data) de diagnóstico aprimorados para manter os Windows seguros, atualizados, solucionar problemas e fazer melhorias no produto. A configuração de dados de diagnóstico aprimorado inclui informações mais detalhadas sobre os dispositivos inscritos no Área de Trabalho Gerenciada da Microsoft e suas configurações, recursos e a saúde do dispositivo. Quando os dados de diagnóstico aprimorados são selecionados, os dados, incluindo os dados de diagnóstico necessários, são coletados. Consulte [Changes to Windows diagnostic data collection](/windows/privacy/changes-to-windows-diagnostic-data-collection) para obter mais informações sobre a configuração Windows 10 dados de diagnóstico e coleta de dados.

A terminologia de dados de diagnóstico mudará em versões futuras do Windows. Área de Trabalho Gerenciada da Microsoft está comprometido com o processamento apenas dos dados necessários ao serviço. Embora isso significa que o nível de diagnóstico mudará para **Opcional,** Área de Trabalho Gerenciada da Microsoft implementará as políticas de diagnóstico limitadas para ajustar a coleta de dados de diagnóstico necessária para o serviço. Para obter mais detalhes, consulte [Changes to Windows diagnostic data collection](/windows/privacy/changes-to-windows-diagnostic-data-collection).

Área de Trabalho Gerenciada da Microsoft processa e armazena dados no nível do sistema Windows 10 dados de diagnóstico opcionais provenientes de dispositivos inscritos, como informações de confiabilidade e desempenho de aplicativos e dispositivos. Área de Trabalho Gerenciada da Microsoft processa e armazena dados pessoais dos clientes, como histórico de chat e navegador, voz, texto ou dados de fala. 

Para obter mais informações sobre a coleção de dados de diagnóstico do Microsoft Windows 10, consulte a seção [Onde](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) armazenamos e processemos dados pessoais da Declaração de Privacidade da Microsoft.

## <a name="microsoft-windows-update-for-business"></a>Microsoft Windows Update for Business
O Microsoft Windows Update for Business usa dados Windows diagnósticos para analisar o status e as falhas de atualização. Área de Trabalho Gerenciada da Microsoft aproveita esses dados e os usa para mitigar e resolver problemas para garantir que todos os dispositivos registrados estão atualizados com base em uma cadência de atualização predefinida.

## <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
A identificação dos dados usados pelo Área de Trabalho Gerenciada da Microsoft é armazenada pelo Azure Active Directory (Azure AD) em uma localização geográfica com base no local fornecido pela organização ao inscrever-se nos serviços online da Microsoft, como o Microsoft Apps para empresas e o Azure. A identificação dos dados usados pelo Área de Trabalho Gerenciada da Microsoft é armazenada pelo Azure AD em uma localização geográfica com base no local fornecido pela organização ao inscrever-se em serviços online da Microsoft, como o Microsoft Apps para empresas e o Azure. Para obter mais informações sobre onde seus dados do Azure AD estão localizados, [consulte Azure Active Directory - Onde seus dados estão localizados?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune coleta, processa e compartilha dados para Área de Trabalho Gerenciada da Microsoft para dar suporte a operações e serviços comerciais. Consulte [Coleta de dados no Intune](/mem/intune/protect/privacy-data-collect) para obter mais informações sobre os dados coletados no Intune. 

Para obter mais informações sobre Microsoft Intune de dados, consulte [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide). O Intune respeita as seleções de local de armazenamento feitas pelo administrador para dados do cliente.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para Ponto de Extremidade
O Microsoft Defender para Ponto de Extremidade coleta e armazena informações para dispositivos inscritos no Área de Trabalho Gerenciada da Microsoft para fins de administração, controle e relatório. As informações coletadas incluem dados de arquivo (como nomes de arquivo, tamanho e hashes), dados de processo (processos em execução, hashes), dados do Registro, dados de conexão de rede e detalhes do dispositivo (como identificadores de dispositivo, nomes de dispositivo e a versão do sistema operacional). Consulte [Microsoft Defender for Endpoint data storage and privacy](/microsoft-365/security/defender-endpoint/data-storage-privacy?view=o365-worldwide#what-data-does-microsoft-defender-atp-collect) para obter mais informações sobre o Microsoft Defender para locais de coleta e armazenamento de dados do Endpoint. 

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps para Grandes Empresas 
Microsoft 365 Apps para Grandes Empresas coleta e compartilha dados com Área de Trabalho Gerenciada da Microsoft para garantir que esses aplicativos estão atualizados com a versão mais recente com base em canais de atualização predefinidos gerenciados pelo Área de Trabalho Gerenciada da Microsoft. Consulte [Microsoft Defender for Endpoint data storage and privacy](/microsoft-365/security/defender-endpoint/data-storage-privacy?view=o365-worldwide#what-data-does-microsoft-defender-atp-collect) para obter mais informações sobre Microsoft 365 Apps de coleta de dados e locais de armazenamento da Microsoft 365 Apps.

## <a name="major-data-change-notification"></a>Notificação de alteração de dados principais
Área de Trabalho Gerenciada da Microsoft segue um processo de controle de alteração conforme descrito em nossa estrutura de comunicação de serviço. Notificamos os clientes Microsoft 365 Central de Mensagens e Área de Trabalho Gerenciada da Microsoft Portal de Administração dos incidentes de segurança e das principais alterações no serviço. Alterações nos tipos de dados coletados e onde são armazenados são consideradas uma alteração material. Forneceremos no mínimo 30 dias de notificação avançada dessa alteração, como é prática padrão para Microsoft 365 produtos e serviços. Para obter mais informações, consulte [Alterações de serviço e comunicação](/microsoft-365/managed-desktop/service-description/servicechanges?view=o365-worldwide).

## <a name="compliance"></a>Conformidade
Área de Trabalho Gerenciada da Microsoft passou por auditorias externas e obteve um conjunto abrangente de ofertas de conformidade. Você pode encontrar mais informações em Área de Trabalho Gerenciada da Microsoft [Conformidade](/microsoft-365/managed-desktop/intro/compliance). Os relatórios de auditoria estão disponíveis para download no [Microsoft Service Trust Portal](https://aka.ms/stp), que funciona como um repositório central para o Microsoft Enterprise Online Services. (Área de Trabalho Gerenciada da Microsoft está listado dentro desses documentos na categoria "Monitoramento e Gerenciamento". 

## <a name="legal"></a>Jurídico
Aviso de privacidade da **Microsoft** para usuários finais de produtos fornecidos por clientes organizacionais - A Declaração de Privacidade da [Microsoft](https://privacy.microsoft.com/privacystatement) notifica os usuários finais que, quando eles fazem login nos produtos microsoft com uma conta de trabalho, a) sua organização pode controlar e administrar sua conta (incluindo controlar as configurações relacionadas à privacidade) e acessar e processar seus dados, e b) a Microsoft pode coletar e processar os dados para fornecer o serviço à organização e aos usuários finais.
