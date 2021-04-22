---
title: Exemplos de políticas de controle de dispositivo para o Intune
description: Saiba como usar políticas de controle de dispositivo usando exemplos que podem ser usados com o Intune.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, dispositivo, controle, usb, removível, mídia, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a7521a31b0b31fb95d2729f7068bfc9de5717f01
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933812"
---
# <a name="examples-of-device-control-policies-for-intune"></a><span data-ttu-id="a4683-104">Exemplos de políticas de controle de dispositivo para o Intune</span><span class="sxs-lookup"><span data-stu-id="a4683-104">Examples of device control policies for Intune</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4683-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a4683-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4683-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a4683-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a4683-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4683-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a4683-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a4683-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a4683-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a4683-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a4683-110">Este documento contém exemplos de políticas de controle de dispositivo que você pode personalizar para sua própria organização.</span><span class="sxs-lookup"><span data-stu-id="a4683-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="a4683-111">Esses exemplos serão aplicáveis se você estiver usando o Intune para gerenciar dispositivos em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="a4683-111">These examples are applicable if you are using Intune to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="a4683-112">Restringir o acesso a todas as mídias removíveis</span><span class="sxs-lookup"><span data-stu-id="a4683-112">Restrict access to all removable media</span></span>

<span data-ttu-id="a4683-113">O exemplo a seguir restringe o acesso a todas as mídias removíveis.</span><span class="sxs-lookup"><span data-stu-id="a4683-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="a4683-114">Observe a permissão que é aplicada no nível superior da política, o que significa que todas as operações de arquivo `none` serão desprovidas.</span><span class="sxs-lookup"><span data-stu-id="a4683-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>none</string> 
                        </array> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="a4683-115">Definir todas as mídias removíveis como somente leitura</span><span class="sxs-lookup"><span data-stu-id="a4683-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="a4683-116">O exemplo a seguir configura todas as mídias removíveis para serem somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a4683-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="a4683-117">Observe a permissão que é aplicada no nível superior da política, o que significa que todas as operações de gravação e execução `read` serão desprovidas.</span><span class="sxs-lookup"><span data-stu-id="a4683-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string> 
                        </array> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="a4683-118">Excluir a execução do programa de mídia removível</span><span class="sxs-lookup"><span data-stu-id="a4683-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="a4683-119">O exemplo a seguir mostra como a execução de programas de mídia removível pode ser desprovada.</span><span class="sxs-lookup"><span data-stu-id="a4683-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="a4683-120">Observe as `read` permissões e que são `write` aplicadas no nível superior da política.</span><span class="sxs-lookup"><span data-stu-id="a4683-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string>
                            <string>write</string> 
                        </array> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist> 
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="a4683-121">Restringir todos os dispositivos de fornecedores específicos</span><span class="sxs-lookup"><span data-stu-id="a4683-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="a4683-122">O exemplo a seguir restringe todos os dispositivos de fornecedores específicos (nesse caso, identificados `fff0` por e `4525` ).</span><span class="sxs-lookup"><span data-stu-id="a4683-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="a4683-123">Todos os outros dispositivos não serão restritos, pois a permissão definida no nível superior da política lista todas as permissões possíveis (leitura, gravação e execução).</span><span class="sxs-lookup"><span data-stu-id="a4683-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string>
                            <string>write</string>
                            <string>execute</string> 
                        </array> 
                        <key>vendors</key> 
                        <dict> 
                            <key>fff0</key> 
                            <dict> 
                                <key>permission</key> 
                                <array> 
                                    <string>none</string> 
                                </array> 
                            </dict> 
                            <key>4525</key> 
                            <dict> 
                                <key>permission</key> 
                                <array>                         
                                    <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="a4683-124">Restringir dispositivos específicos identificados pela ID do fornecedor, ID do produto e número de série</span><span class="sxs-lookup"><span data-stu-id="a4683-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="a4683-125">O exemplo a seguir restringe dois dispositivos específicos, identificados por ID do fornecedor, ID do produto `fff0` e números de série e `1000` `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` .</span><span class="sxs-lookup"><span data-stu-id="a4683-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="a4683-126">Em todos os outros níveis da política, as permissões incluem todos os valores possíveis (leitura, gravação e execução), o que significa que todos os outros dispositivos serão irrestritos.</span><span class="sxs-lookup"><span data-stu-id="a4683-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string>
                            <string>write</string>
                            <string>execute</string>
                        </array> 
                        <key>vendors</key> 
                        <dict> 
                            <key>fff0</key> 
                            <dict> 
                                <key>permission</key> 
                                <array> 
                                    <string>read</string> 
                                    <string>write</string>
                                    <string>execute</string> 
                                </array> 
                                <key>products</key> 
                                <dict> 
                                    <key>1000</key> 
                                    <dict> 
                                        <key>permission</key> 
                                        <array> 
                                            <string>read</string> 
                                            <string>write</string>
                                            <string>execute</string>
                                        </array> 
                                        <key>serialNumbers</key> 
                                        <dict> 
                                            <key>04ZSSMHI2O7WBVOA</key> 
                                            <array> 
                                            <string>none</string> 
                                            </array> 
                                            <key>04ZSSMHI2O7WBVOB</key>
                                            <array> 
                                            <string>none</string> 
                                            </array> 
                                        </dict> 
                                    </dict> 
                                </dict> 
                            </dict>
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="related-topics"></a><span data-ttu-id="a4683-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a4683-127">Related topics</span></span>

- [<span data-ttu-id="a4683-128">Visão geral do controle de dispositivo para macOS</span><span class="sxs-lookup"><span data-stu-id="a4683-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
