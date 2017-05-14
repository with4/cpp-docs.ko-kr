---
title: "&lt;bitset&gt; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<bitset>
- std.<bitset>
- <bitset>
dev_langs:
- C++
helpviewer_keywords:
- <bitset> header
- bitset header
ms.assetid: af30a9b9-489e-46e3-9d29-5f3ea07ae6dc
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: d0b9f494cec6212616813f9d622b97ff9d54bd3e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="ltbitsetgt"></a>&lt;bitset&gt;
템플릿 클래스 bitset 및 고정 크기 비트 시퀀스를 나타내고 조작하기 위한 두 개의 지원 템플릿 함수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#include <bitset>  
  
```  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator&](../standard-library/bitset-operators.md#op_amp)|두 bitset 간에 비트 AND를 수행합니다.|  
|[operator<\<](../standard-library/bitset-operators.md#op_lt_lt)|비트 시퀀스의 텍스트 표현을 표준 출력 스트림에 삽입합니다.|  
|[operator>>](../standard-library/bitset-operators.md#op_gt_gt)|비트 시퀀스의 텍스트 표현을 표준 입력 스트림에 삽입합니다.|  
|[operator^](../standard-library/bitset-operators.md#op_xor)|두 bitset 간에 비트 EXCLUSIVE-OR을 수행합니다.|  
|[operator&#124;](../standard-library/bitset-operators.md#op_or)|두 bitset 간에 비트 OR을 수행합니다.|  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[bitset 클래스](../standard-library/bitset-class.md)|이 템플릿 클래스는 일련의 항목 또는 조건에 대한 플래그를 유지하기 위한 간단한 방법으로 제공하는 고정된 비트 수로 구성된 시퀀스를 저장하는 개체 형식을 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)




