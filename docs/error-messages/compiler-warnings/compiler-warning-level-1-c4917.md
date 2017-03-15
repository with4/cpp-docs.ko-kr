---
title: "컴파일러 경고 (수준 1) C4917 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4917
dev_langs:
- C++
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 7
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
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: 43dce460fb336b09ce39d3e4c0e52b43a175ea36
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4917"></a>컴파일러 경고(수준 1) C4917
'declarator': GUID만 클래스, 인터페이스 또는 네임 스페이스와 연결할 수  
  
이외의 다른 사용자 정의 구조 [클래스](../../cpp/class-cpp.md), [인터페이스](../../cpp/interface.md), 또는 [네임 스페이스](../../cpp/namespaces-cpp.md) GUID를 가질 수 없습니다.  
  
기본적으로 이 경고는 해제되어 있습니다. 참조 [기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 에 대 한 자세한 내용은 합니다.  
  
## <a name="example"></a>예제  
다음 코드 샘플에서는 C4917 오류가 생성 됩니다.  
  
```cpp  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```
