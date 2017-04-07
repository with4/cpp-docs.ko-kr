---
title: "컴파일러 오류 C2435 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 53a3144fe8e87f36a1a5149d292130a9913b646a
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-error-c2435"></a>컴파일러 오류 C2435
'var': 동적 초기화는 관리 되는 CRT 필요, /clr: safe를 컴파일할 수 없습니다  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 응용 프로그램별 도메인 전역 변수는 초기화로 컴파일된 CRT가 필요 `/clr:pure`를 확인할 수 있는 이미지를 생성 하지 않는 합니다.  
  
 자세한 내용은 참조 [appdomain](../../cpp/appdomain.md) 및 [프로세스](../../cpp/process.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2435 오류가 생성 됩니다.  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
