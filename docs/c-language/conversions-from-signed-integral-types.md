---
title: "부호 있는 정수 형식에서 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: d7ed58066cecc42492f3b163b130ff8a4ef53ed0
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="conversions-from-signed-integral-types"></a>부호 있는 정수 계열 형식에서 변환
부호 있는 정수를 크기가 같거나 더 큰 부호 없는 정수로 변환하는데 부호 있는 정수의 값이 음수가 아니면 값이 변경되지 않습니다. 변환은 부호 있는 정수를 부호 확장하여 수행됩니다. 부호 있는 정수는 상위 비트를 잘라 더 짧은 부호 있는 정수로 변환됩니다. 결과는 이 예제에서 볼 수 있는 것과 같이 부호 없는 값으로 해석됩니다.  
  
```  
int i = -3;  
unsigned short u;  
  
u = i;   
printf_s( "%hu\n", u );  // Prints 65533  
  
```  
  
 **long int** 또는 **unsigned long int** 값을 **float** 값으로 변환할 때 정밀도가 다소 손실될 수 있다는 점을 제외하면 부호 있는 정수를 부동 값으로 변환할 때 아무 정보도 손실되지 않습니다.  
  
 다음 표에서는 부호 있는 정수 계열 형식으로부터의 변환을 요약하여 보여 줍니다. 이 표에서는 **char** 형식에 기본적으로 부호가 있다고 간주합니다. 컴파일 시간 옵션을 사용하여 **char** 형식의 기본값을 unsigned로 변경할 경우 다음 표인 "부호 있는 정수 형식에서 변환" 대신 **unsigned char** 형식에 대한 [부호 없는 정수 형식에서 변환](../c-language/conversions-from-unsigned-integral-types.md) 표에 나와 있는 변환이 적용됩니다.  
  
### <a name="conversions-from-signed-integral-types"></a>부호 있는 정수 계열 형식에서 변환  
  
|시작|후|메서드|  
|----------|--------|------------|  
|**char**1|**short**|부호 확장|  
|**char**|**long**|부호 확장|  
|**char**|**unsigned char**|패턴 유지(상위 비트가 부호 비트로의 기능을 잃음)|  
|**char**|**unsigned short**|**short**로 부호 확장(**short**를 **unsigned short**로 변환)|  
|**char**|**unsigned long**|**short**로 부호 확장(**long**을 **unsigned long**으로 변환)|  
|**char**|**float**|**long**으로 부호 확장(**long**을 **float**로 변환)|  
|**char**|**double**|**long**으로 부호 확장(**long**을 **double**로 변환)|  
|**char**|**long double**|**long**으로 부호 확장(**long**을 **double**로 변환)|  
|**short**|**char**|하위 바이트 유지|  
|**short**|**long**|부호 확장|  
|**short**|**unsigned char**|하위 바이트 유지|  
|**short**|**unsigned short**|비트 패턴 유지(상위 비트가 부호 비트로의 기능을 잃음)|  
|**short**|**unsigned long**|**short**로 부호 확장(**long**을 **unsigned long**으로 변환)|  
|**short**|**float**|**long**으로 부호 확장(**long**을 **float**로 변환)|  
|**short**|**double**|**long**으로 부호 확장(**long**을 **double**로 변환)|  
|**short**|**long double**|**long**으로 부호 확장(**long**을 **double**로 변환)|  
|**long**|**char**|하위 바이트 유지|  
|**long**|**short**|하위 단어 유지|  
|**long**|**unsigned char**|하위 바이트 유지|  
|**long**|**unsigned short**|하위 단어 유지|  
|**long**|**unsigned long**|비트 패턴 유지(상위 비트가 부호 비트로의 기능을 잃음)|  
|**long**|**float**|**float**로 표시. **long**을 정확히 나타낼 수 없는 경우 일부 정밀도가 손실됩니다.|  
|**long**|**double**|**double**로 표시. **long**을 **double**로 정확히 나타낼 수 없는 경우 일부 정밀도가 손실됩니다.|  
|**long**|**long double**|**double**로 표시. **long**을 **double**로 정확히 나타낼 수 없는 경우 일부 정밀도가 손실됩니다.|  
  
 1. 모든 **char** 항목에서는 **char** 형식에 기본적으로 부호가 있다고 간주합니다.  
  
 **Microsoft 전용**  
  
 Microsoft 32비트 C 컴파일러의 경우 정수는 **long**과 동일합니다. **int** 값의 변환은 **long**과 동일하게 진행됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [할당 변환](../c-language/assignment-conversions.md)
