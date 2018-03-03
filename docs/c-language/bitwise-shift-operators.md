---
title: "비트 시프트 연산자 | Microsoft Docs"
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
- operators [C++], bitwise
- shift operators, bitwise
- bitwise-shift operators
- operators [C++], shift
ms.assetid: d0485785-5c72-47e1-a7c0-0adde03ade23
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e13e65e42febf2256e11bcb428e98805cdd6550f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bitwise-shift-operators"></a>비트 시프트 연산자
시프트 연산자는 두 번째 피연산자가 지정하는 위치 수만큼 첫 번째 피연산자를 왼쪽(`<<`) 또는 오른쪽(`>>`)으로 이동합니다.  
  
## <a name="syntax"></a>구문  
 *shift-expression*:  
 *additive-expression*  
  
 *shift-expression*  `<<`  *additive-expression shift-expression*  `>>`  *additive-expression*  
  
 피연산자는 둘 다 정수 계열 값이어야 합니다. 이러한 연산자는 일반적인 산술 변환을 수행하며, 결과의 형식은 변환 후 왼쪽 피연산자의 형식입니다.  
  
 왼쪽으로 이동하는 경우 비워진 오른쪽 비트는 0으로 설정됩니다. 오른쪽으로 이동하는 경우 비워진 왼쪽 비트는 변환 후 첫 번째 피연산자의 형식에 따라 채워집니다. 형식이 `unsigned`이면 0으로 설정되고, 그렇지 않으면 부호 비트를 복사하여 채워집니다. 오버플로가 없는 왼쪽 시프트 연산자의 경우 다음 문은  
  
```  
expr1 << expr2   
```  
  
 2<sup>expr2</sup>를 곱한 값과 같습니다. 오른쪽 시프트 연산자의 경우 다음 문은  
  
```  
expr1 >> expr2   
```  
  
 `expr1`이 부호가 없거나 음수가 아닌 값인 경우 2<sup>expr2</sup>로 나눈 값과 같습니다.  
  
 두 번째 피연산자가 음수인 경우나 오른쪽 피연산자가 확장된 왼쪽 피연산자의 너비(비트)보다 크거나 같은 경우 시프트 연산의 결과가 정의되지 않습니다.  
  
 시프트 연산자로 수행된 변환은 오버플로 또는 언더플로 조건을 지원하지 않으므로 변환 후 시프트 연산의 결과가 첫 번째 피연산자의 형식으로 표현될 수 없는 경우 정보가 손실될 수 있습니다.  
  
```  
unsigned int x, y, z;  
  
x = 0x00AA;  
y = 0x5500;  
  
z = ( x << 8 ) + ( y >> 8 );  
```  
  
 이 예제에서 `x`는 8개 위치만큼 왼쪽으로 이동하고 `y`는 8개 위치만큼 오른쪽으로 이동합니다. 이동된 두 값을 더하여 0XAA55가 생성되고 `z`에 할당됩니다.  
  
 음수 값을 오른쪽으로 이동하면 원래 값의 반을 정수로 내림한 값이 생성됩니다. 예를 들어 –253(이진수 11111111 00000011)을 오른쪽으로 1비트 이동하면 –127(이진수 11111111 10000001)이 생성됩니다. 양수 253을 오른쪽으로 이동하면 +126이 생성됩니다.  
  
 오른쪽 시프트는 기호 비트를 유지합니다. 부호 있는 정수가 오른쪽으로 이동하면 최상위 비트는 설정된 상태로 유지됩니다. 부호 없는 정수가 오른쪽으로 이동하면 최상위 비트는 해제됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [왼쪽 시프트 및 오른쪽 시프트 연산자(>> 및 <<)](../cpp/left-shift-and-right-shift-operators-input-and-output.md)