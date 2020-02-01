---
title: Exibir informações sobre arquivos mal-intencionados detectados no SharePoint, no OneDrive ou no Microsoft Teams
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Saiba onde ir para exibir informações sobre arquivos mal-intencionados detectados no SharePoint, no OneDrive ou no Microsoft Teams e como executar ações nesses arquivos.
ms.openlocfilehash: 49c7e1668602a63b8b82339ad0cc7823146212a4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599008"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="2fe6c-103">Exibir informações sobre arquivos mal-intencionados detectados no SharePoint, no OneDrive ou no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2fe6c-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="2fe6c-104">O [Office 365 ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) protege sua organização de arquivos mal-intencionados em bibliotecas de documentos e sites de equipe.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="2fe6c-105">Quando um arquivo mal-intencionado é detectado, esse arquivo é bloqueado para que ninguém possa abri-lo, copiá-lo ou compartilhá-lo até que outras ações sejam executadas pela equipe de segurança da organização.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="2fe6c-106">Leia este artigo para saber como exibir informações sobre arquivos detectados e quais ações executar.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="2fe6c-107">Para executar as tarefas descritas neste artigo, você deve ter as [permissões necessárias para o centro de conformidade de segurança &amp; do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2fe6c-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="2fe6c-108">Exibir relatórios com informações sobre arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="2fe6c-108">View reports with information about detected files</span></span>

<span data-ttu-id="2fe6c-109">Para exibir o status e informações detalhadas sobre arquivos detectados pelo Office 365 ATP, você pode usar o relatório de status de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="2fe6c-110">No [centro de conformidade de &amp; segurança do Office 365](https://protection.office.com), escolha **painel** \> de **relatórios** \> **status da proteção contra ameaças**.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="2fe6c-111">No canto superior direito do relatório, escolha **Exibir tabela de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="2fe6c-112">Exiba a lista de arquivos que foram detectados no relatório.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="2fe6c-113">Selecione um item na lista para exibir informações detalhadas, incluindo ações executadas, o nome do arquivo, o caminho do arquivo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="2fe6c-114">Escolha a guia **análise avançada** para exibir informações, como comportamento observado e detalhes da análise.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="2fe6c-115">Exibir e executar ação em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="2fe6c-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="2fe6c-116">No centro de conformidade de &amp; segurança do Office 365, escolha **quarentena**de **análise** \> de **Gerenciamento** \> de ameaças.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="2fe6c-117">(Você também pode ir diretamente para [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span><span class="sxs-lookup"><span data-stu-id="2fe6c-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="2fe6c-118">No canto superior esquerdo, altere o menu suspenso de **emails** para **arquivos**.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="2fe6c-119">Se a lista de resultados incluir muitos itens, use a funcionalidade de **filtro** para restringir a seleção.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="2fe6c-120">Selecione um item na lista para exibir informações detalhadas, incluindo a URL do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="2fe6c-121">Escolha uma ação disponível.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-121">Choose an available action.</span></span>
    
  - <span data-ttu-id="2fe6c-122">Escolha o **arquivo de lançamento** para desbloquear o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-122">Choose **Release file** to unblock the file.</span></span> 
    
    <span data-ttu-id="2fe6c-123">Selecione **Enviar relatório para a Microsoft** para relatar o arquivo como um falso positivo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="2fe6c-124">Escolha **baixar arquivo** para investigar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-124">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="2fe6c-125">Escolha **remover da quarentena** para remover o arquivo da lista de itens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="2fe6c-126">Se você escolher essa opção, também deverá excluir o arquivo de sua respectiva biblioteca no SharePoint Online, no OneDrive for Business ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="2fe6c-127">Essa opção não desbloqueia um arquivo de ser aberto ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="2fe6c-128">Escolha **fechar** para fechar os detalhes de um item selecionado.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

