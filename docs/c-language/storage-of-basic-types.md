---
title: "기본 형식의 저장소 | Microsoft Docs"
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
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5a42f5c0e4592fc397ac51d610ed6ca1495c4504
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="storage-of-basic-types"></a>기본 형식의 저장소
다음 표에서는 각 기본 형식과 관련된 저장소에 대해 요약합니다.  
  
### <a name="sizes-of-fundamental-types"></a>기본 형식의 크기  
  
|형식|저장소|  
|----------|-------------|  
|`char`, `unsigned char`, **signed char**|1바이트|  
|**short**, **unsigned short**|2바이트|  
|`int`, `unsigned int`|4바이트|  
|**long**, `unsigned long`|4바이트|  
|**float**|4바이트|  
|**double**|8바이트|  
|`long double`|8바이트|  
  
 C 데이터 형식은 일반 범주로 분류됩니다. "정수 계열 형식"에는 `char`, `int`, **short**, **long**, **signed**, `unsigned` 및 `enum`이 포함됩니다. "부동 형식"에는 **float**, **double** 및 `long double`이 포함됩니다. "산술 형식"에는 모든 부동 및 정수 형식이 포함됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 및 형식](../c-language/declarations-and-types.md)
