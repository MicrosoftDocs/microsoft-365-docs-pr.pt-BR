---
title: Colaborar com pessoas de fora da sua organização
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba como configurar aplicativos da Microsoft 365 como o Teams, o OneDrive e o SharePoint para colaboração com pessoas de fora da sua organização.
ms.openlocfilehash: 374ad8f5ec37fc0900fb38cb4e0f4743a02c4da4
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613449"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="f2e23-103">Colaborar com pessoas de fora da sua organização</span><span class="sxs-lookup"><span data-stu-id="f2e23-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="f2e23-104">Os recursos de compartilhamento externo no Microsoft 365 oferecem uma oportunidade para que as pessoas em sua organização colaborem com parceiros, fornecedores, clientes e outros que não tenham uma conta no seu diretório.</span><span class="sxs-lookup"><span data-stu-id="f2e23-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="f2e23-105">Você pode compartilhar equipes ou sites inteiros com pessoas de fora da sua organização ou apenas arquivos individuais.</span><span class="sxs-lookup"><span data-stu-id="f2e23-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="f2e23-106">Colaborar com pessoas de fora da sua organização consiste em dois componentes principais:</span><span class="sxs-lookup"><span data-stu-id="f2e23-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="f2e23-107">**Habilitar compartilhamento** : Configure os controles de compartilhamento no Azure Active Directory, nas equipes, nos grupos do Microsoft 365 e no SharePoint para permitir o nível de compartilhamento que você deseja para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f2e23-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="f2e23-108">**Habilitar segurança adicional** -embora os recursos de compartilhamento básicos possam ser configurados para exigir que pessoas de fora da sua organização autentiquem, a Microsoft 365 fornece vários recursos de segurança e conformidade adicionais para ajudá-lo a proteger seus dados e manter suas políticas de governança ao compartilhar externamente.</span><span class="sxs-lookup"><span data-stu-id="f2e23-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="f2e23-109">Habilitar o compartilhamento</span><span class="sxs-lookup"><span data-stu-id="f2e23-109">Enable sharing</span></span>

<span data-ttu-id="f2e23-110">Por padrão, no Microsoft 365, o compartilhamento com pessoas de fora da sua organização é habilitado para o SharePoint e o OneDrive, mas desabilitado para o Teams.</span><span class="sxs-lookup"><span data-stu-id="f2e23-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="f2e23-111">Muitos cenários de compartilhamento externo do SharePoint e do OneDrive funcionam sem nenhuma configuração adicional.</span><span class="sxs-lookup"><span data-stu-id="f2e23-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="f2e23-112">Para confirmar as configurações de um cenário que você está usando ou habilitar um novo, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f2e23-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="f2e23-113">[Colaborar em documentos](collaborate-on-documents.md) – saiba como configurar o Microsoft 365 para permitir o compartilhamento e a colaboração com pessoas de fora da sua organização (convidados e usuários não autenticados) em arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="f2e23-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="f2e23-114">[Colaborar em um site](collaborate-in-site.md) -saiba como configurar o Microsoft 365 para habilitar o compartilhamento de sites do SharePoint com convidados.</span><span class="sxs-lookup"><span data-stu-id="f2e23-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="f2e23-115">[Colaborar como uma equipe](collaborate-as-team.md) – saiba como configurar o Microsoft 365 para habilitar a colaboração de convidados no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2e23-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="f2e23-116">Para obter uma visão abrangente das configurações de compartilhamento de convidados disponíveis no Microsoft 365, consulte [referência de configurações de compartilhamento de convidados da Microsoft 365](microsoft-365-guest-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f2e23-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="f2e23-117">Habilitar segurança adicional</span><span class="sxs-lookup"><span data-stu-id="f2e23-117">Enable additional security</span></span>

<span data-ttu-id="f2e23-118">Depois de habilitar o cenário que você deseja usar para compartilhar com pessoas de fora da sua organização, considere as proteções adicionais para ajudar a proteger o conteúdo de um compartilhamento inadequado ou intencionalmente intencionado.</span><span class="sxs-lookup"><span data-stu-id="f2e23-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="f2e23-119">[Práticas recomendadas para o compartilhamento de arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md) : Saiba mais sobre as práticas recomendadas para o compartilhamento com usuários não autenticados.</span><span class="sxs-lookup"><span data-stu-id="f2e23-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="f2e23-120">[Limitar exposição acidental](share-limit-accidental-exposure.md) : saiba como reduzir as chances de compartilhar acidentalmente conteúdo confidencial com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f2e23-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="f2e23-121">[Criar um ambiente de compartilhamento seguro de convidados](create-secure-guest-sharing-environment.md) : Saiba mais sobre as ferramentas fornecidas no Microsoft 365 para ajudar a garantir que o compartilhamento com pessoas de fora da sua organização seja feito de forma segura e segura e atenda aos requisitos de governança.</span><span class="sxs-lookup"><span data-stu-id="f2e23-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="f2e23-122">Colaborar com empresas parceiras</span><span class="sxs-lookup"><span data-stu-id="f2e23-122">Collaborate with partner companies</span></span>

<span data-ttu-id="f2e23-123">Quando você estiver trabalhando em um projeto grande que envolve muitos convidados de outra organização, ou se você tiver uma relação de fornecedor contínua em que os convidados estão freqüentemente mudando, você pode usar o gerenciamento de qualificação no Azure Active Directory para simplificar o gerenciamento de convidados e permitir que a empresa parceira Compartilhe com essa responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="f2e23-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="f2e23-124">Consulte [criar uma extranet B2B com convidados gerenciados](b2b-extranet.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="f2e23-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="f2e23-125">Limitar o compartilhamento</span><span class="sxs-lookup"><span data-stu-id="f2e23-125">Limit sharing</span></span>

<span data-ttu-id="f2e23-126">Se alguns dos recursos de compartilhamento no Microsoft 365 estão em conflito com suas políticas de governança, confira [limitar o compartilhamento no microsoft 365](microsoft-365-limit-sharing.md) para saber mais sobre as opções para limitar o compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="f2e23-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2e23-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f2e23-127">Related topics</span></span>

[<span data-ttu-id="f2e23-128">Introdução à colaboração de arquivos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f2e23-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="f2e23-129">Planejar a colaboração de arquivos no SharePoint com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f2e23-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
