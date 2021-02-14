---
title: Referência de configurações configuráveis para a Área de Trabalho Gerenciada da Microsoft
description: Definindo categorias para configurações configuráveis na Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c7c7d75fad58cab0cd6d19a16a97667ea3641a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104483"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referência de configurações configuráveis - Área de Trabalho Gerenciada da Microsoft

Este tópico lista as categorias de configurações que os clientes podem configurar com a Área de Trabalho Gerenciada da Microsoft. Cada categoria de configuração inclui informações sobre requisitos, práticas recomendadas e como personalizar a categoria de configuração. 

## <a name="desktop-background-picture"></a>Imagem de plano de fundo da área de trabalho
Você pode personalizar a imagem de plano de fundo da área de trabalho para dispositivos da Área de Trabalho Gerenciada da Microsoft em sua organização. Você pode usar isso para aplicar uma marca da empresa ou material de marketing. 

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para uma imagem de plano de fundo da área de trabalho:
- Formato de arquivo de imagem - .jpg, jpeg ou .png
- Local do arquivo - Host em um local http seguro confiável (https). 
- Não permitido - Locais http e de compartilhamento de arquivos (unc) não são suportados. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizar e implantar imagem de plano de fundo da área de trabalho

**Para adicionar uma imagem de plano de fundo personalizada da área de trabalho**
1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. No **espaço de trabalho Configurações,** selecione a imagem de plano de fundo da área de **trabalho.** 
4. Insira o local da imagem que você deseja usar. 
5. Selecione **Implantação de Estágio** para salvar suas alterações e implantá-las no grupo teste. 

## <a name="browser-start-pages"></a>Páginas inciais do navegador
As páginas inciais do navegador abrem em guias individuais quando os usuários iniciam o Microsoft Edge. Se você quiser facilitar a abertura de um conjunto de sites que eles usam com frequência, adicione uma página inicial do navegador para cada site. 

### <a name="requirements"></a>Requisitos

Você deve fornecer o FQDN (nome de domínio totalmente qualificado) para sites da intranet ou da Internet para as páginas inciais do navegador. Se os sites internos estão configurados, avise aos usuários que o acesso a esses sites só é permitido quando conectado à rede interna no escritório ou quando conectado com uma conexão VPN. 

### <a name="customize-and-deploy-browser-start-pages"></a>Personalizar e implantar páginas inciais do navegador

**Para adicionar uma página inicial do navegador**
1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. In **Settings** workspace, select **Browser start pages**. 
4. Selecione **Adicionar página inicial.**
5. Em **Adicionar página inicial do navegador,** insira a URL do site que você deseja usar e selecione Adicionar página **inicial.** 
6. Repita as etapas 1 a 5 para páginas inciais adicionais do navegador. 
7. Selecione **Implantação de Estágio** para salvar suas alterações e implantá-las no grupo teste.

## <a name="enterprise-mode-site-list-location"></a>Local da lista de sites do modo Empresarial

Se você tiver sites e aplicativos específicos que você sabe que têm problemas de compatibilidade com o Microsoft Edge, poderá usar a lista de sites do modo Empresarial para que os sites abram automaticamente usando o Internet Explorer 11. Além disso, se você sabe que seus sites da intranet não funcionarão corretamente com o Microsoft Edge, poderá definir todos os sites da intranet para abrir usando o Internet Explorer 11 automaticamente. Usar o modo Empresarial significa que você pode continuar a usar o Microsoft Edge como navegador padrão, garantindo também que seus aplicativos continuem funcionando no Internet Explorer 11. Para obter mais informações sobre listas de sites do modo empresarial, consulte [Enterprise Mode e Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

Você pode especificar um https:// local ou o local de um compartilhamento interno onde você hospedou sua lista de sites do modo empresarial. 

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para o arquivo de lista de sites do modo Empresarial:
- Formato de arquivo - arquivo XML que atende aos [requisitos de arquivo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Local do arquivo - Arquivo host em um local https interno. 
- Não permitido - A hospedagem em um compartilhamento de arquivos interno, como *//sharename,* não é permitida

### <a name="best-practices"></a>Práticas recomendadas

Essas práticas recomendadas são oferecidas para ajudar os clientes a tomar decisões para modernizar sua infraestrutura de TI:
- **Escolha um número limitado de sites** – a Área de Trabalho Gerenciada da Microsoft usa o Microsoft Edge como navegador preferencial para melhorar a segurança geral da sua organização e a usabilidade para seus usuários. A maioria dos sites nesta lista são para aplicativos Web herdada que precisam de uma versão mais antiga de um navegador que não incluirá tantos recursos de segurança. 
- **Considere uma alternativa** – considere um site diferente ou um aplicativo Web que não exige um navegador mais antigo. Ou considere atualizar o site para que ele possa usar navegadores mais novos. Os navegadores mais recentes usam a tecnologia mais recente e ajudam a melhorar a segurança.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalizar e implantar o local da lista de sites do modo Empresarial

**Para adicionar um local de lista de modo de site corporativo**

1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. No **espaço de trabalho Configurações,** selecione o local da lista de sites do modo **Empresarial.** 
4. Insira o local https para sua lista de sites. 
5. Selecione **Implantação de Estágio** para salvar suas alterações e implantá-las no grupo teste.

## <a name="trusted-sites"></a>Sites confiáveis

Sites confiáveis permitem que você personalize zonas de segurança, ou onde um site pode ser usado, para sites diferentes. As zonas de segurança incluem: 
- Zona 1 – Zona da Intranet Local
- Zona 2 – Zona de sites confiáveis
- Zona 3 – Zona da Internet
- Zona 4 – Zona de Sites Restritos

### <a name="requirements"></a>Requisitos

Forneça o nome de domínio totalmente qualificado (FQDN) para sites da intranet ou da Internet para cada site confiável. 

### <a name="customize-and-deploy-trusted-sites"></a>Personalizar e implantar sites confiáveis

**Para adicionar um site confiável**

1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. No **espaço de** trabalho Configurações, selecione Sites **confiáveis** e, em seguida, **selecione Adicionar site confiável.** 
4. Em **Adicionar site confiável,** insira a URL, escolha uma zona de segurança e selecione **Adicionar site confiável.** 
5. Repita as etapas 1 a 4 para cada site confiável que você deseja adicionar. 
6. Selecione **Implantação de Estágio** para salvar suas alterações e implantá-las no grupo teste.

**Para remover um site confiável**

1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. No **espaço de trabalho** Configurações, selecione Sites **confiáveis.** 
4. Selecione o site que você deseja excluir e, em seguida, **selecione Excluir**. 
5. Repita as etapas 1 a 4 para cada site confiável que você deseja excluir. 
6. Selecione **Implantação de Estágio** para salvar suas alterações e implantá-las no grupo teste.

## <a name="proxy"></a>Proxy
Você pode gerenciar as configurações de proxy de rede para sua organização. Adicione o servidor proxy e o número da porta e, em seguida, adicione suas exceções de site proxy. A Área de Trabalho Gerenciada da Microsoft inclui um conjunto de exceções de proxy padrão que são necessárias para o serviço operar. A lista de exclusão padrão só pode ser modificada pelo serviço área de trabalho gerenciada da Microsoft.  Para obter mais informações, consulte [Configuração de rede da Área de Trabalho Gerenciada da Microsoft.](../get-ready/network.md) 

As exceções de site proxy adicionadas no portal da Área de Trabalho Gerenciada da Microsoft são adicionadas às exceções de proxy padrão incluídas no serviço de Área de Trabalho Gerenciada da Microsoft. 

> [!NOTE]
> A atualização da lista de exceções de proxy padrão é sempre priorizada em relação às implantações do cliente. Isso significa que sua implantação em estágios será pausada se houver uma implantação para a lista de exceções de proxy padrão.  

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para exceções de servidor proxy e site proxy:
- Deve ser um endereço de servidor e um número de porta válidos
- AS URLs devem ser um site http válido 

### <a name="customize-and-deploy-proxies"></a>Personalizar e implantar proxies

**Para adicionar uma exceção de site proxy individual**

1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. No **espaço de trabalho** Configurações, selecione **Proxy**. 
4. Insira o **número do** endereço e **da porta** do servidor proxy e selecione **Adicionar exceção de proxy.** 
5. Insira a URL de um site http válido e selecione **Adicionar exceção de proxy.** 
6. Repita as etapas 1 a 5 para cada site confiável que você deseja adicionar. 
7. Selecione **Implantação de Estágio** para salvar suas alterações e implantá-las no grupo teste.

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral de configurações configuráveis](config-setting-overview.md) 
- [Implantar configurações que podem ser alteradas](config-setting-deploy.md)
