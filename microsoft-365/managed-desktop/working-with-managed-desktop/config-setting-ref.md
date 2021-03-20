---
title: Referência de configurações configuráveis para Área de Trabalho Gerenciada da Microsoft
description: Definindo categorias para configurações configuráveis na Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917699"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referência de configurações configuráveis - Área de Trabalho Gerenciada da Microsoft

Este tópico lista as categorias de configurações que os clientes podem configurar com a Área de Trabalho Gerenciada da Microsoft. Cada categoria de configuração inclui informações sobre requisitos, práticas recomendadas e como personalizar a categoria de configuração. 

## <a name="desktop-background-picture"></a>Imagem em segundo plano da área de trabalho
Você pode personalizar a imagem em segundo plano da área de trabalho para dispositivos da Área de Trabalho Gerenciada da Microsoft em sua organização. Você pode usar isso para aplicar uma marca da empresa ou material de marketing. 

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para uma imagem em segundo plano da área de trabalho:
- Formato de arquivo de imagem - .jpg, jpeg ou .png
- Local do arquivo - Host em um local http (https) seguro confiável. 
- Não permitido - Locais de http e compartilhamento de arquivos (unc) não são suportados. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizar e implantar imagem em segundo plano da área de trabalho

**Para adicionar uma imagem de plano de fundo da área de trabalho personalizada**
1. Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.
3. Em **Espaço de trabalho Configurações,** selecione Imagem de plano de fundo da área de **trabalho**. 
4. Insira o local da imagem que você deseja usar. 
5. Selecione **Estágio de implantação** para salvar suas alterações e implantá-las no grupo Teste. 

## <a name="browser-start-pages"></a>Páginas de início do navegador
As páginas de início do navegador são abertas em guias individuais quando os usuários iniciam o Microsoft Edge. Se você quiser facilitar a abertura de um conjunto de sites que eles usam com frequência, adicione uma página inicial do navegador para cada site. 

### <a name="requirements"></a>Requisitos

Você deve fornecer o FQDN (nome de domínio totalmente qualificado) para intranet ou sites da Internet para as páginas de início do navegador. Se os sites internos estão configurados, deixe os usuários saberem que o acesso a esses sites só é permitido quando conectado à rede interna quando no escritório ou quando conectado a uma conexão VPN. 

### <a name="customize-and-deploy-browser-start-pages"></a>Personalizar e implantar páginas de início do navegador

**Para adicionar uma página inicial do navegador**
1. Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.
3. Em **Espaço de trabalho** Configurações, selecione Páginas in início do **navegador**. 
4. Selecione **Adicionar página inicial**.
5. Em **Adicionar página inicial do navegador,** insira a URL do site que você deseja usar e selecione Adicionar página **inicial**. 
6. Repita as etapas 1 a 5 para páginas de início adicionais do navegador. 
7. Selecione **Estágio de implantação** para salvar suas alterações e implantá-las no grupo Teste.

## <a name="enterprise-mode-site-list-location"></a>Local da lista de sites do modo empresarial

Se você tiver sites e aplicativos específicos que você sabe que têm problemas de compatibilidade com o Microsoft Edge, poderá usar a lista de sites do Modo Empresarial para que os sites abram automaticamente usando o Internet Explorer 11. Além disso, se você sabe que seus sites de intranet não funcionarão corretamente com o Microsoft Edge, você pode definir todos os sites da intranet para abrir usando o Internet Explorer 11 automaticamente. Usar o Modo Empresarial significa que você pode continuar a usar o Microsoft Edge como navegador padrão, além de garantir que seus aplicativos continuem funcionando no Internet Explorer 11. Para obter mais informações sobre listas de sites do modo empresarial, consulte [Enterprise Mode e Enterprise Mode Site Lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

Você pode especificar um https:// local ou o local de um compartilhamento interno onde você hospedou sua lista de sites do modo empresarial. 

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para o arquivo de lista de sites do modo empresarial:
- Formato de arquivo - arquivo XML que atende aos requisitos [de arquivo](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Local do arquivo - arquivo host em um local https interno. 
- Não permitido - A hospedagem em um compartilhamento de arquivos interno, como *//sharename*, não é permitida

### <a name="best-practices"></a>Práticas recomendadas

Essas práticas recomendadas são oferecidas para ajudar os clientes a tomar decisões para modernizar sua infraestrutura de TI:
- **Escolha um número limitado de sites** – a Área de Trabalho Gerenciada da Microsoft usa o Microsoft Edge como navegador preferencial para melhorar a segurança geral da sua organização e a usabilidade para seus usuários. A maioria dos sites nesta lista são para aplicativos Web herdada que precisam de uma versão mais antiga de um navegador que não incluirá tantos recursos de segurança. 
- **Considere um alternativo** – considere um site ou aplicativo Web diferente que não exige um navegador mais antigo. Ou, considere atualizar o site para que ele possa usar navegadores mais novos. Os navegadores mais recentes usam a tecnologia mais recente e ajudam a melhorar a segurança.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalizar e implantar o local da lista do modo de site empresarial

**Para adicionar um local de lista do modo de site empresarial**

1. Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.
3. Em **Espaço de trabalho Configurações,** selecione Local da lista de sites do modo **empresarial**. 
4. Insira o local https para sua lista de sites. 
5. Selecione **Estágio de implantação** para salvar suas alterações e implantá-las no grupo Teste.

## <a name="trusted-sites"></a>Sites confiáveis

Sites confiáveis permitem personalizar zonas de segurança ou onde um site pode ser usado para sites diferentes. As zonas de segurança incluem: 
- Zona 1 – Zona de Intranet Local
- Zona 2 – Zona de sites confiáveis
- Zona 3 – Zona da Internet
- Zona 4 – Zona de Sites Restritos

### <a name="requirements"></a>Requisitos

Forneça o FQDN (nome de domínio totalmente qualificado) para intranet ou sites da Internet para cada site confiável. 

### <a name="customize-and-deploy-trusted-sites"></a>Personalizar e implantar sites confiáveis

**Para adicionar um site confiável**

1. Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.
3. Em **Espaço de trabalho** Configurações, selecione Sites **confiáveis** e, em seguida, **selecione Adicionar site confiável**. 
4. Em **Adicionar site confiável,** insira a URL, escolha uma zona de segurança e selecione **Adicionar site confiável**. 
5. Repita as etapas 1 a 4 para cada site confiável que você deseja adicionar. 
6. Selecione **Estágio de implantação** para salvar suas alterações e implantá-las no grupo Teste.

**Para remover um site confiável**

1. Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.
3. No **espaço de trabalho** Configurações, selecione Sites **confiáveis**. 
4. Selecione o site que você deseja excluir e selecione **Excluir**. 
5. Repita as etapas 1 a 4 para cada site confiável que você deseja excluir. 
6. Selecione **Estágio de implantação** para salvar suas alterações e implantá-las no grupo Teste.

## <a name="proxy"></a>Proxy
Você pode gerenciar configurações de proxy de rede para sua organização. Adicione seu servidor proxy e número de porta e adicione suas exceções de site de proxy. A Área de Trabalho Gerenciada da Microsoft inclui um conjunto de exceções de proxy padrão que são necessárias para o serviço operar. A lista de exclusão padrão só pode ser modificada pelo serviço de Área de Trabalho Gerenciada da Microsoft.  Para obter mais informações, consulte [Configuração de rede para Área de Trabalho Gerenciada da Microsoft.](../get-ready/network.md) 

As exceções de site proxy adicionadas no portal da Área de Trabalho Gerenciada da Microsoft são adicionadas às exceções de proxy padrão incluídas no serviço de Área de Trabalho Gerenciada da Microsoft. 

> [!NOTE]
> A atualização da lista de exceções de proxy padrão é sempre priorizada em relação às implantações do cliente. Isso significa que sua implantação em estágios será pausada se houver uma implantação para a lista de exceções de proxy padrão.  

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para exceções de site de proxy e servidor proxy:
- Deve ser um endereço de servidor válido e um número de porta
- URLs devem ser um site http válido 

### <a name="customize-and-deploy-proxies"></a>Personalizar e implantar proxies

**Para adicionar uma exceção de site de proxy individual**

1. Entre no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações**.
3. Em **Espaço de trabalho** Configurações, selecione **Proxy**. 
4. Insira o **endereço e** o número **da porta** para o servidor proxy e selecione **Adicionar exceção de proxy**. 
5. Insira a URL de um site http válido e selecione **Adicionar exceção de proxy.** 
6. Repita as etapas 1 a 5 para cada site confiável que você deseja adicionar. 
7. Selecione **Estágio de implantação** para salvar suas alterações e implantá-las no grupo Teste.

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral das configurações configuráveis](config-setting-overview.md) 
- [Implantar configurações que podem ser alteradas](config-setting-deploy.md)