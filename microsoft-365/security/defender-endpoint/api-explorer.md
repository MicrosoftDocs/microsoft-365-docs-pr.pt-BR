---
title: API Explorer no Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Use o Explorador de API para criar e fazer consultas de API, testar e enviar solicitações para qualquer API disponível
keywords: api, explorer, send, request, get, post,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769792"
---
# <a name="api-explorer"></a><span data-ttu-id="e9dbc-104">Explorador de API</span><span class="sxs-lookup"><span data-stu-id="e9dbc-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9dbc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e9dbc-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9dbc-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e9dbc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="e9dbc-107">O Microsoft Defender for Endpoint API Explorer é uma ferramenta que ajuda você a explorar várias APIs do Defender para Ponto de Extremidade interativamente.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="e9dbc-108">O Explorador de API facilita a construção e o desenvolvimento de consultas, testes e solicitações de API para qualquer ponto de extremidade da API do Defender para Ponto de Extremidade disponível.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="e9dbc-109">Use o Explorador de API para tomar ações ou encontrar dados que ainda não estão disponíveis por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="e9dbc-110">A ferramenta é útil durante o desenvolvimento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-110">The tool is useful during app development.</span></span> <span data-ttu-id="e9dbc-111">Ele permite que você execute consultas de API que respeitem as configurações de acesso do usuário, reduzindo a necessidade de gerar tokens de acesso.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="e9dbc-112">Você também pode usar a ferramenta para explorar a galeria de consultas de exemplo, copiar exemplos de código de resultado e gerar informações de depuração.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="e9dbc-113">Com o Explorador de API, você pode:</span><span class="sxs-lookup"><span data-stu-id="e9dbc-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="e9dbc-114">Executar solicitações para qualquer método e ver respostas em tempo real</span><span class="sxs-lookup"><span data-stu-id="e9dbc-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="e9dbc-115">Navegue rapidamente pelos exemplos de API e saiba quais parâmetros eles suportam</span><span class="sxs-lookup"><span data-stu-id="e9dbc-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="e9dbc-116">Fazer chamadas de API com facilidade; não é necessário autenticar além do portal de gerenciamento entrar</span><span class="sxs-lookup"><span data-stu-id="e9dbc-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="e9dbc-117">Explorador de API do Access</span><span class="sxs-lookup"><span data-stu-id="e9dbc-117">Access API Explorer</span></span>

<span data-ttu-id="e9dbc-118">No menu de navegação esquerdo, selecione **Parceiros & APIs API**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="e9dbc-119">APIs com suporte</span><span class="sxs-lookup"><span data-stu-id="e9dbc-119">Supported APIs</span></span>

<span data-ttu-id="e9dbc-120">O Api Explorer dá suporte a todas as APIs oferecidas pelo Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="e9dbc-121">A lista de APIs com suporte está disponível na documentação [de APIs](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="e9dbc-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="e9dbc-122">Começar com o Explorador de API</span><span class="sxs-lookup"><span data-stu-id="e9dbc-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="e9dbc-123">No painel esquerdo, há uma lista de solicitações de exemplo que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="e9dbc-124">Siga os links e clique em **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="e9dbc-125">Alguns dos exemplos podem exigir a especificação de um parâmetro na URL, por exemplo, {machine-ID}.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="e9dbc-126">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="e9dbc-126">FAQ</span></span>

<span data-ttu-id="e9dbc-127">**Preciso ter um token de API para usar o Explorador de API?**</span><span class="sxs-lookup"><span data-stu-id="e9dbc-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="e9dbc-128">Credenciais para acessar uma API não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="e9dbc-129">O Explorador de API usa o token do portal de gerenciamento do Defender for Endpoint sempre que faz uma solicitação.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="e9dbc-130">A credencial de autenticação de usuário conectado é usada para verificar se o Explorador de API está autorizado a acessar dados em seu nome.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="e9dbc-131">Solicitações de API específicas são limitadas com base em seus privilégios RBAC.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="e9dbc-132">Por exemplo, uma solicitação para "Enviar indicador" está limitada à função de administrador de segurança.</span><span class="sxs-lookup"><span data-stu-id="e9dbc-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
