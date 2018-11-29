---
title: Requisitos do aplicativo Microsoft Desktop gerenciados
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864663"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisitos do aplicativo Microsoft Desktop gerenciados

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Aplicativos de linha de negócios que você deseja implantar para os dispositivos de área de trabalho gerenciada do Microsoft devem atender aos requisitos neste tópico. 

## <a name="application-condition"></a>Condição de aplicativo

É importante que os aplicativos não afetam adversamente o ambiente de área de trabalho gerenciada do Microsoft. A seguir estão os requisitos que precisa atender a um aplicativo na ordem para a Microsoft implantá-lo. Para qualquer determinado aplicativo ou driver, Microsoft talvez cancelamento qualquer requisito fornecido aqui. Microsoft poderá optar por remover qualquer aplicativo ou driver que afeta negativamente o desempenho e confiabilidade de dispositivos do Microsoft Desktop gerenciados.

## <a name="deployable-using-microsoft-technologies"></a>Implantáveis usando tecnologias da Microsoft

Microsoft Desktop gerenciados usa Intune, Microsoft Store e Microsoft Store for Business para implantar aplicativos. Consequentemente, os aplicativos devem ser empacotados de maneira que poderão ser implantados pela versão atual desses serviços.

## <a name="prohibited-app-classes"></a>Classes de app proibido

Certos tipos de aplicativo não são permitidos em dispositivos Microsoft Desktop gerenciados:
- 3º antivírus de terceiros, segurança ou software de auditoria
- Versões do Microsoft Office anteriores ao Office 365 Pro Plus
- Aplicativos que instalam ou agrupam os outros softwares de terceiros 3º

## <a name="restricted-app-behaviors"></a>Comportamentos de app restritos

Determinados comportamentos de aplicativo podem ser ser prejudicial a experiência do usuário ou representam um risco de segurança para dispositivos Microsoft Desktop gerenciados. Aplicativos não devem apresentar os seguintes comportamentos ou características: 
- Instalar os serviços de plano de fundo ou disparar processos de plano de fundo de execução longa
- Se adicionar ao caminho de inicialização do Windows
- Chamar não documentado Windows ou as APIs de escritório ou assumir dependências nas estruturas de dados internas do Windows ou do Office
- Atuar como um repositório de app ou que o Gerenciador de extensão interna
- Eleva os privilégios do usuário final
- Ter vulnerabilidades de segurança conhecidas
- Assinados com um certificado que não acumular uma raiz confiável
- Criptografar ou restringir o acesso aos dados do usuário final
- Modificar o código de sistema operacional em tempo de execução

## <a name="driver-deployment"></a>Implantação do driver

A menos que um driver está disponível no Windows Update ou separadamente é assinado pelo laboratório de qualidade de Hardware para Windows (WHQL), Microsoft deve aprovar um driver antes que o Microsoft implantará o driver dispositivos Microsoft Desktop gerenciados.