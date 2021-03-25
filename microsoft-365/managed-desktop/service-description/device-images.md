---
title: Imagens do dispositivo
description: Requisitos de imagem ao ordenar novos dispositivos ou reutilar dispositivos existentes
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 9a263cbc6bdd0d521e835f086967a6f7236c6948
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166291"
---
# <a name="device-images"></a>Imagens do dispositivo


Se você solicitar [novos dispositivos](#new-devices) ou [reutilizar](#existing-devices) os existentes, você tem várias opções para garantir que a imagem no dispositivo atenda aos nossos [requisitos de dispositivo.](device-requirements.md#check-hardware-requirements)

## <a name="new-devices"></a>Novos dispositivos
Ao solicitar um novo dispositivo de um fabricante [aprovado,](device-requirements.md#minimum-requirements)siga estas etapas para garantir que eles shipem dispositivos com a configuração de software e imagem da Área de Trabalho Gerenciada da Microsoft correta.

### <a name="dell"></a>Dell
Trabalhe diretamente com o representante de vendas da Dell, que garantirá que a imagem aprovada pela Área de Trabalho Gerenciada da Microsoft seja aplicada a dispositivos para seu pedido. Para obter mais perguntas sobre dispositivos Dell, a imagem e o processo de ordenação, entre em contato MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
Ao solicitar novos dispositivos da HP, certifique-se de usar o SKU específico listado na seção Requisitos adicionais para cada modelo, conforme mostrado em [Dispositivos de programa](device-list.md#hp).

Se você estiver ordenando um dispositivo da HP [](customizing.md) que foi aprovado como uma exceção, mas não está listado no momento na página Lista de Dispositivos, solicite que o SKU seja usado para seu modelo. Trabalharemos com a HP para obter essas informações usando sua solicitação de exceção. Você também pode contatar a HP diretamente para obter qualquer dúvida sobre dispositivos e instruções de ordenação de dispositivos usando estes endereços:
 
- Américas: mmd-americas@hp.com
- Europa/Oriente Médio/África: mmd-emea@hp.com
- Pacífico Asiático/Japão: mmd-apj@hp.com
- Global: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Ao solicitar dispositivos da Lenovo para uso na Área de Trabalho Gerenciada da Microsoft, você precisará indicar um número de parte específico incluído como parte da ordem. Entre em contato com o representante de vendas da Lenovo ou o Parceiro de Canal da Lenovo e peça que eles criem um "*modelo* de oferta especial " com um sistema que atenda aos nossos [requisitos de dispositivo.](device-requirements.md#minimum-requirements) Para incluir uma imagem pré-carregada compatível com a Área de Trabalho Gerenciada da Microsoft, peça ao representante de vendas para fazer referência a " número da parte de bloco de construção do sistema *SBB0Q94938 – Habilitar MMD*".

No momento, os seguintes produtos estão habilitados para suporte à Área de Trabalho Gerenciada da Microsoft:

- L13 Gen 1
- L13 Yoga Gen 1
- L14 Gen 1 (Intel)
- L14 Gen 1 (AMD)
- L15 Gen 1 (Intel)
- L15 Gen 1 (AMD)
- X1 Carbon Gen 8
- X1 Yoga Gen 5
- T14 Gen 1 (Intel)
- T14 Gen 1 (AMD)
- T15 Gen 1
- X13 Gen 1 (Intel)


### <a name="microsoft"></a>Microsoft
Todos os dispositivos Microsoft que atendem aos requisitos do dispositivo vêm com uma imagem que funciona com a Área de Trabalho Gerenciada da Microsoft. Nenhuma outra etapa é necessária.

Para obter a imagem mais recente disponível na fábrica em um dispositivo Microsoft, trabalhe com seu especialista do Surface para usar o processo surface "Pegged PO".

## <a name="existing-devices"></a>Dispositivos existentes

Você pode reutilizar dispositivos existentes desde que eles atendem aos requisitos de [dispositivo](device-requirements.md#minimum-requirements) e aos [requisitos de software.](device-requirements.md#installed-software) Siga as etapas relevantes para o fabricante.

Você pode reimager dispositivos com uma imagem do fabricante ou usando a "imagem universal" da Área de Trabalho Gerenciada da Microsoft. Para obter uma imagem apropriada do fabricante, você pode solicitar pelo menos [um](#new-devices) novo dispositivo do modelo que está reutilizável. Em seguida, você pode obter a imagem desse dispositivo e aplicá-la a outros dispositivos do mesmo modelo exato.

> [!NOTE]
> Você é responsável por criar, testar e implantar imagens. Também recomendamos usar imagens apropriadas fornecidas pelo fabricante sempre que possível, em vez de imagens personalizadas, incluindo a "imagem universal".

### <a name="hp"></a>HP

Os PCs comerciais HP fornecidos com o HP Corporate Ready Image incluem um . Arquivo WIM para recuperação. Você pode usar essa imagem para aplicar a imagem de restauração de fábrica a outros dispositivos do mesmo modelo.

Essas etapas removerão todos os dados no dispositivo, portanto, antes de começar, você deve fazer o back up de todos os dados que deseja manter.

1. [Crie uma unidade USB inicializável](https://docs.microsoft.com/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) com WinPE.
2. Copie esses arquivos de C: \\ SOURCES para a unidade USB:
    - O arquivo WIM de recuperação de fábrica (por exemplo, HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC CR \_ \_ \_ 2004.wim)
    - IMPLANTAR. CMD
    - ReCreatePartitions.txt
3. [Inicializar o dispositivo para WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) Unidade USB.
4. Em um prompt de comando, execute [Diskpart.exe](https://docs.microsoft.com/windows-server/administration/windows-commands/diskpart#additional-references).
5. Em Diskpart, execute e anote o número de disco de armazenamento principal `list disk` (normalmente, Disco 0).
6. Saia diskpart digitando `exit` .
7. No prompt de comando, execute , onde sys_disk é o número de disco do disco de armazenamento principal que você acabou de determinar e recovery_wim é o `deploy.cmd <sys_disk> <recovery_wim>` nome de arquivo do .   Arquivo WIM copiado anteriormente.
8. Remova a unidade USB e reinicie o dispositivo.

### <a name="microsoft"></a>Microsoft 

Os dispositivos Microsoft Surface incluem imagens de "recuperação de bare [metal"](https://support.microsoft.com/en-us/surfacerecoveryimage) específicas para cada modelo. Você pode usar essas imagens para reaginar dispositivos.

Essas imagens usam o Ambiente de Recuperação do Windows (WinRE) e esse é um processo manual (não automatizado). Siga as etapas em [Criar e usar uma unidade de recuperação USB para Surface](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07).


### <a name="universal-image"></a>Imagem universal
A Área de Trabalho Gerenciada da Microsoft criou uma imagem que contém o Windows 10 Pro e o Microsoft 365 Apps para Empresas que você pode usar com a Área de Trabalho Gerenciada da Microsoft. No entanto, é melhor usar imagens apropriadas à Área de Trabalho Gerenciada da Microsoft fornecidas pelo fabricante sempre que possível, mesmo que isso signifique uma versão mais antiga do Windows que, em seguida, precisa ser atualizada quando o usuário entrar. Usar a imagem Universal da Área de Trabalho Gerenciada da Microsoft deve ser uma opção final.

- Atualizamos a imagem com as atualizações de qualidade mensal mais recentes do Windows a cada 30 a 60 dias e atualizações do Microsoft 365 Apps for Enterprise pelo menos duas vezes por ano.
- A imagem contém um pacote de provisionamento de recuperação para garantir que o Microsoft 365 Apps for Enterprise seja restaurado seguindo os cenários de recuperação do Windows.
- Você pode implantar a imagem com unidades USB. Ele contém um processo que pode ser roteado para inserir drivers (descritos na documentação incluída na imagem).
- Você pode modificar os scripts e pastas incluídos para uso com outras personalizações, como adicionar atualizações cumulativas específicas, código de cópia de arquivo ou executar outras verificações.
- Drivers e atualizações de qualidade são adicionados ao Windows durante a implantação da unidade USB.

> [!NOTE]
> É sua responsabilidade adicionar todos os drivers necessários, executar todos os testes e garantir que não haja problemas com a imagem final implantada. Fornecemos a Imagem Universal "como está" mas fornecerá orientações técnicas e responderá perguntas. Contate MMDImage@microsoft.com.

Enviar solicitações para o conteúdo e documentação da Imagem Universal criando uma solicitação de alteração no [portal de administração](../get-started/access-admin-portal.md).


