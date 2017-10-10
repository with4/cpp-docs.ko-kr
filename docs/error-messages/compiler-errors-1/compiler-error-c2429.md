---
title: "컴파일러 오류 C2429 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 18fd64199ff043b660bb205199b982ee2843cdcd
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2429"></a>컴파일러 오류 C2429
'*언어 기능*'컴파일러 플래그 필요'*컴파일러 옵션*'  
  
언어 기능 지원에 대 한 특정 컴파일러 옵션을 사용 해야 합니다.  
  
오류 C2429: 언어 기능 ' 중첩 된 네임 스페이스-정의 ' 필요 컴파일러 플래그 ' / std:c + + 최신 ' 정의 하려는 경우에 생성 되는 *복합 네임 스페이스*, 하나 이상의 범위를 중첩 된 네임 스페이스 이름을 포함 하는 네임 스페이스 를 Visual Studio 2015 업데이트 3에서 시작 합니다. 복합 네임 스페이스 정의 C + + 17 하기 전에 c + +에서 사용할 수 없습니다. 컴파일러 복합 네임 스페이스 정의 지원 때는 [/std:c + + 최신](../../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 지정 합니다.  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
