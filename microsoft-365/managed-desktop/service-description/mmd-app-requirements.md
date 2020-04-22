---
title: Requisitos do aplicativo da área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5889a4e80f44349b4f149ee4f2a631f12b32251e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637847"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisitos do aplicativo da área de trabalho gerenciada da Microsoft

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
Para garantir o desempenho, a confiabilidade e a manutenção dos dispositivos de área de trabalho gerenciada da Microsoft, os aplicativos de linha de negócios do cliente não precisam afetar seriamente a experiência do usuário final ou modificar a postura de segurança. Consequentemente, os aplicativos de linha de negócios que você deseja implantar para os dispositivos de área de trabalho gerenciada da Microsoft devem atender aos requisitos neste tópico.

## <a name="application-condition"></a>Condição de aplicativo

É importante que os aplicativos não afetem negativamente o ambiente de área de trabalho gerenciada da Microsoft. A seguir estão os requisitos que um aplicativo deve atender para um aplicativo a ser implantado. Para qualquer aplicativo ou driver específico, a Microsoft pode renunciar a qualquer requisito fornecido aqui. A Microsoft pode decidir remover qualquer aplicativo ou driver que impacta negativamente o desempenho e a confiabilidade dos dispositivos de área de trabalho gerenciado da Microsoft.

## <a name="centrally-managed-apps"></a>Aplicativos gerenciados de forma centralizada

Todos os aplicativos e drivers instalados em dispositivos gerenciados pela Microsoft devem ser implantados por meio do Microsoft Intune, da Microsoft Store ou da Microsoft Store para empresas; Se estiver disponível, os drivers também serão implantados por meio do serviço Windows Update. 

## <a name="prohibited-app-classes"></a>Classes de aplicativo proibidas

Determinados tipos de aplicativos não são permitidos em dispositivos de área de trabalho gerenciada da Microsoft:
- software antivírus, de segurança ou de auditoria de terceiros
- Versões do Microsoft Office anteriores ao Microsoft 365 Apps for Enterprise
- Aplicativos que instalam ou agrupam outros softwares de terceiros

## <a name="restricted-app-behaviors"></a>Comportamentos de aplicativo restritos

Determinados comportamentos de aplicativo podem afetar negativamente a experiência do usuário ou podem representar um risco de segurança para os dispositivos de área de trabalho gerenciada da Microsoft. Os aplicativos com os seguintes comportamentos não podem ser executados no ambiente de área de trabalho gerenciada da Microsoft sem um específico da Microsoft.

Experiência do usuário:
- Instalar serviços em segundo plano
- Adicione a si próprio ao caminho de inicialização do Windows
- Aplicativos dependentes de drivers
- navegadores da Web de terceiros

Segurança:
- Elevar os privilégios do usuário final
- Atuar como uma loja de aplicativos ou ter um Gerenciador de extensões interno
- Ter vulnerabilidades de segurança conhecidas
- Criptografar ou restringir o acesso aos dados do usuário final
- Não está assinado ou assinado usando um certificado que não se acumula em uma raiz confiável


## <a name="driver-deployment"></a>Implantação de driver

A área de trabalho gerenciada da Microsoft suporta apenas drivers de dispositivos que estão disponíveis por meio do Windows Update ou da caixa de entrada instalada com o dispositivo gerenciado da Microsoft. 

Se um aplicativo exigir que um ou mais drivers específicos sejam executados, será considerado um aplicativo restrito e exigirá uma exceção antes de ser implantado na área de trabalho gerenciada da Microsoft. 

