---
title: "컴파일러 오류 C2393 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 078454c9824a734863796ab5810056147d17879c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2393"></a>컴파일러 오류 C2393
'symbol': '세그먼트' 세그먼트에는 appdomain 별 기호를 할당할 수 없습니다  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않습니다.  
  
 사용 [appdomain](../../cpp/appdomain.md) 변수를 컴파일하는 것을 의미 **/clr: pure** 또는 **/clr: safe**, 안전 또는 순수 이미지 데이터 세그먼트를 포함할 수 없습니다.  
  
 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 에 대 한 자세한 내용은 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2393 오류가 발생 합니다.  
  
```  
// C2393.cpp  
// compile with: /clr:pure /c  
#pragma data_seg("myseg")  
int n = 0;   // C2393  
```
