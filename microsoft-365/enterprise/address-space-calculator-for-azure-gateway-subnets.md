---
title: Calculadora de espaço de endereço para sub-redes de gateway do Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/07/2021
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
description: 'Resumo: Calcule o espaço de endereço de uma sub-rede de gateway do Azure com C3, Python ou PowerShell.'
ms.openlocfilehash: d92bea5c36fde6277154d19365ed0bdaa5df4254
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780563"
---
# <a name="address-space-calculator-for-azure-gateway-subnets"></a>Calculadora de espaço de endereço para sub-redes de gateway do Azure

Uma rede virtual (VNet) nos serviços de infraestrutura do Azure conectada a outras redes deve ter uma sub-rede de gateway. As práticas recomendadas para definir a sub-rede do gateway são:

- O comprimento do prefixo da sub-rede de gateway pode ter um comprimento de prefixo máximo de 29 (por exemplo, 10.119.255.248/29), mas a recomendação atual é que você use um comprimento de prefixo de 27 (por exemplo, 10.119.255.224/27).
- Ao definir o espaço de endereço da sub-rede do gateway, use a última parte do espaço de endereço VNet.

Para a segunda recomendação, você pode determinar o espaço de endereço da sub-rede do gateway definindo os bits usados para a sub-rede de gateway como 0 e os bits restantes no espaço de endereço VNet como 1. Para calcular rapidamente o espaço de endereço de sub-rede do gateway sem precisar converter em binário e voltar para decimal, você pode usar um aplicativo de console escrito em C# ou Python ou com um bloco de comandos do PowerShell.

Este artigo contém C#, Python e blocos de código do PowerShell que calculam o espaço de endereço da sub-rede do gateway com base nos valores de w.x.y.z/n para o prefixo de endereço VNet e o comprimento do prefixo de sub-rede do gateway.

## <a name="c-code-block"></a>C# de código

Use esse bloco de código para criar um aplicativo de console C#.

```c#
using System; 
using System.Collections.Generic; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 
 
namespace ConsoleApplication1 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // Declare variables. 
            const long wOctet = 16777216;  
            const long xOctet = 65536; 
            const long yOctet = 256; 
            double D; 
            int w, x, y, z, vnetPrefLen, gwPrefLen; 
            long d, w2, x2, y2, z2; 
             
 
            // Get the five values needed from the keyboard. 
            Console.WriteLine("**************************************************************************"); 
            Console.WriteLine("**_ Gateway subnet address space calculator for Azure virtual networks _*_");             
            Console.WriteLine("_*************************************************************************");  
            Console.WriteLine(); 
            Console.WriteLine("Please supply your virtual network address space in the form of w.x.y.z/n."); 
            Console.WriteLine(); 
            Console.WriteLine("w="); 
            w = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("x="); 
            x = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("y="); 
            y = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("z="); 
            z = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("n="); 
            vnetPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
            Console.WriteLine("Now supply the prefix length of your gateway subnet:"); 
            gwPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
 
            // Perform the calculation. 
            D = w * wOctet + x * xOctet + y * yOctet + z; 
            for (int i = vnetPrefLen + 1; i < gwPrefLen + 1; i++) 
            { 
                D = D + Math.Pow(2, 32 - i); 
            } 
            d = Convert.ToInt64(D); 
            w2 = d / wOctet; 
            x2 = (d - w2 * wOctet) / xOctet;  
            y2 = (d - w2 * wOctet - x2 * xOctet) / yOctet; 
            z2 = d - w2 * wOctet - x2 * xOctet - y2 * yOctet; 
             
            // Display the result.             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine("For the Azure virtual address space {0}.{1}.{2}.{3}/{4}", w, x, y, z, vnetPrefLen); 
            Console.WriteLine("and gateway prefix length of {0}, the gateway subnet address space is:", gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("{0}.{1}.{2}.{3}/{4}", w2, x2, y2, z2, gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("Press ENTER to quit."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="python-code-block"></a>Bloco de código Python

Use esse bloco de código para criar um aplicativo de console no Python.

```python
import math 
# Collect the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet 
print("**************************************************************************")  
print("**_ Gateway subnet address space calculator for Azure virtual networks _*_")  
print("_*************************************************************************\n")   
print("Please supply your virtual network address space in the form of w.x.y.z/n.");  
w=int(input("w = ")) 
x=int(input("x = ")) 
y=int(input("y = ")) 
z=int(input("z = ")) 
n=int(input("n = ")) 
print("")  
g=int(input("Now supply the prefix length of your gateway subnet: ")) 
print("")  
 
# Calculate  
wOctet = 16777216  
xOctet = 65536  
yOctet = 256  
D = w * wOctet + x * xOctet + y * yOctet + z 
for index in range(n + 1,g + 1): 
    D += 2**(32 - index)  
 
w2 = math.floor(D / wOctet)  
x2 = math.floor((D - w2 * wOctet) / xOctet) 
y2 = math.floor((D - w2 * wOctet - x2 * xOctet) / yOctet) 
z2 = D - w2 * wOctet - x2 * xOctet - y2 * yOctet  
 
# Display the result  
gwAddrPref= "Your gateway address prefix is: " + str(w2) + "." + str(x2) + "." + str(y2) + "." + str(z2) + "/" + str(g)  
print(gwAddrPref) 
```


## <a name="powershell-command-block"></a>Bloco de comando do PowerShell

Preencha os valores e execute o bloco de comando resultante em uma janela do PowerShell ou no Ambiente de Script Integrado do PowerShell (ISE).

```powershell
# Specify the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet: 
$w= 
$x= 
$y= 
$z= 
$n= 
$g= 
# Calculate 
$wOctet = 16777216 
$xOctet = 65536 
$yOctet = 256 
[long]$D = $w * $wOctet + $x * $xOctet + $y * $yOctet + $z; 
for ($i = $n + 1; $i -lt $g + 1; $i++) 
{ 
$D = $D + [math]::pow(2, 32 - $i) 
} 
$w2 = [math]::floor($D / $wOctet) 
$x2 = [math]::floor( ($D - $w2 * $wOctet) / $xOctet ) 
$y2 = [math]::floor( ($D - $w2 * $wOctet - $x2 * $xOctet) / $yOctet ) 
$z2 = $D - $w2 * $wOctet - $x2 * $xOctet - $y2 * $yOctet 
# Display the result 
$dx= [string]$w2 + "." + [string]$x2 + "." + [string]$y2 + "." + [string]$z2 + "/" + [string]$g 
Write-Host "Your gateway address prefix is: " $dx
```
    
## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)