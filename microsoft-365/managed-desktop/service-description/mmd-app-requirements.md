---
title: Requisitos do aplicativo da área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278331"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisitos do aplicativo da área de trabalho gerenciada da Microsoft

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Os aplicativos de linha de negócios que você deseja implantar para os dispositivos de área de trabalho gerenciado da Microsoft devem atender aos requisitos neste tópico. 

## <a name="application-condition"></a>Condição de aplicativo

É importante que os aplicativos não afetem negativamente o ambiente de área de trabalho gerenciada da Microsoft. A seguir estão os requisitos que um aplicativo deve atender para que a Microsoft o implante. Para qualquer aplicativo ou driver específico, a Microsoft pode renunciar a qualquer requisito fornecido aqui. A Microsoft pode decidir remover qualquer aplicativo ou driver que impacta negativamente o desempenho e a confiabilidade dos dispositivos de área de trabalho gerenciado da Microsoft.

## <a name="deployable-using-microsoft-technologies"></a>ImPlantável usando tecnologias Microsoft

O Microsoft Managed desktop usa o Intune, a Microsoft Store e a Microsoft Store para empresas para implantar aplicativos. Consequentemente, os aplicativos devem ser empacotados de uma maneira que possa ser implantado pela versão atual desses serviços.

## <a name="prohibited-app-classes"></a>Classes de aplicativo proibidas

Determinados tipos de aplicativos não são permitidos em dispositivos de área de trabalho gerenciada da Microsoft:
- software antivírus, de segurança ou de auditoria de terceiros
- navegadores da Web de terceiros
- Versões do Microsoft Office anteriores ao Office 365 Pro Plus
- Aplicativos que instalam ou agrupam outros softwares de terceiros

## <a name="restricted-app-behaviors"></a>Comportamentos de aplicativo restritos

Determinados comportamentos de aplicativos podem ser prejudiciais à experiência do usuário ou apresentar um risco de segurança para os dispositivos de área de trabalho gerenciada da Microsoft. Os aplicativos não devem apresentar os seguintes comportamentos ou características: 

Experiência do usuário:
- Instalar os serviços em segundo plano ou gerar processos em segundo plano de execução longa
- Adicione a si próprio ao caminho de inicialização do Windows

Segurança:
- Chamar as APIs não documentadas do Windows ou do Office ou assumir dependências em estruturas de dados internas do Windows ou do Office
- Atuar como uma loja de aplicativos ou ter um Gerenciador de extensões interno
- Elevar os privilégios do usuário final
- Ter vulnerabilidades de segurança conhecidas
- Assinado usando um certificado que não se acumula em uma raiz confiável
- Criptografar ou restringir o acesso aos dados do usuário final
- Modificar o código do sistema operacional no tempo de execução

## <a name="driver-deployment"></a>Implantação de driver

A menos que um driver esteja disponível no Windows Update ou tenha sido assinado separadamente pelo Windows Hardware Quality Lab (WHQL), a Microsoft deve aprovar um driver antes que a Microsoft implante o driver nos dispositivos da área de trabalho gerenciada da Microsoft.
