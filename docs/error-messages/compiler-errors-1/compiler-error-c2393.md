---
title: "컴파일러 오류 C2393 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a2c4f8d31fb6ddb6eaa9472dc7537edbcdc29054
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2393"></a>컴파일러 오류 C2393
'symbol': 'segment' 세그먼트에 appdomain 별 기호를 할당할 수 없습니다  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 사용 [appdomain](../../cpp/appdomain.md) 변수 의미와 컴파일하는 **/clr: pure** 또는 **/clr: safe**, 안전 또는 순수 이미지는 데이터 세그먼트를 포함할 수 없습니다.  
  
 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2393 오류가 발생 합니다.  
  
```  
// C2393.cpp  
// compile with: /clr:pure /c  
#pragma data_seg("myseg")  
int n = 0;   // C2393  
```
