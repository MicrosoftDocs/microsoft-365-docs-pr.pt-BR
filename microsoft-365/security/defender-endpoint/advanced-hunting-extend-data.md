---
title: Estender a cobertura de busca avançada com as configurações corretas
description: Verifique as configurações de auditoria em dispositivos Windows e outras configurações para ajudar a garantir que você receba os dados mais abrangentes na busca avançada
keywords: busca avançada, incidente, pivô, entidade, configurações de auditoria, gerenciamento de contas de usuário, gerenciamento de grupo de segurança, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, mdatp, Microsoft Defender ATP, Microsoft Defender para Ponto de Extremidade, Windows Defender, Windows Defender ATP, Windows Defender Proteção Avançada contra Ameaças
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500611"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="0492a-104">Estender a cobertura de busca avançada com as configurações corretas</span><span class="sxs-lookup"><span data-stu-id="0492a-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0492a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0492a-105">**Applies to:**</span></span>
- [<span data-ttu-id="0492a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0492a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="0492a-107">[A busca avançada](advanced-hunting-overview.md) depende dos dados provenientes de toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="0492a-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="0492a-108">Para obter os dados mais abrangentes possíveis, verifique se você tem as configurações corretas nas fontes de dados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="0492a-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="0492a-109">Auditoria avançada de segurança em dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="0492a-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="0492a-110">A opção Ativar essas configurações avançadas de auditoria para garantir que você receba dados sobre atividades em seus dispositivos, incluindo gerenciamento de contas locais, gerenciamento de grupo de segurança local e criação de serviço.</span><span class="sxs-lookup"><span data-stu-id="0492a-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="0492a-111">Data</span><span class="sxs-lookup"><span data-stu-id="0492a-111">Data</span></span> | <span data-ttu-id="0492a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="0492a-112">Description</span></span> | <span data-ttu-id="0492a-113">Tabela de esquema</span><span class="sxs-lookup"><span data-stu-id="0492a-113">Schema table</span></span> | <span data-ttu-id="0492a-114">Como configurar</span><span class="sxs-lookup"><span data-stu-id="0492a-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="0492a-115">Account management</span><span class="sxs-lookup"><span data-stu-id="0492a-115">Account management</span></span> | <span data-ttu-id="0492a-116">Eventos capturados como vários `ActionType` valores indicando criação, exclusão e outras atividades relacionadas à conta local</span><span class="sxs-lookup"><span data-stu-id="0492a-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="0492a-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="0492a-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="0492a-118">- Implantar uma política avançada de auditoria de segurança: [Auditar o Gerenciamento de Contas de Usuário](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="0492a-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="0492a-119">- [Saiba mais sobre políticas avançadas de auditoria de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="0492a-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="0492a-120">Gerenciamento de grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="0492a-120">Security group management</span></span> | <span data-ttu-id="0492a-121">Eventos capturados como vários valores indicando a criação de grupos `ActionType` de segurança local e outras atividades de gerenciamento de grupo locais</span><span class="sxs-lookup"><span data-stu-id="0492a-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="0492a-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="0492a-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="0492a-123">- Implantar uma política avançada de auditoria de segurança: [Auditar o Gerenciamento de Grupo de Segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="0492a-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="0492a-124">- [Saiba mais sobre políticas avançadas de auditoria de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="0492a-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="0492a-125">Instalação do serviço</span><span class="sxs-lookup"><span data-stu-id="0492a-125">Service installation</span></span> | <span data-ttu-id="0492a-126">Eventos capturados com `ActionType` o `ServiceInstalled` valor , indicando que um serviço foi criado</span><span class="sxs-lookup"><span data-stu-id="0492a-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="0492a-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="0492a-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="0492a-128">- Implantar uma política avançada de auditoria de segurança: [Auditar a Extensão do Sistema de Segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="0492a-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="0492a-129">- [Saiba mais sobre políticas avançadas de auditoria de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="0492a-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="0492a-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0492a-130">Related topics</span></span>

- [<span data-ttu-id="0492a-131">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="0492a-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0492a-132">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="0492a-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0492a-133">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="0492a-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="0492a-134">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="0492a-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="0492a-135">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="0492a-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="0492a-136">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="0492a-136">Custom detections overview</span></span>](overview-custom-detections.md)
