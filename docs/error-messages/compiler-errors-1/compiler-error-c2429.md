---
title: "컴파일러 오류 C2429 | Microsoft 문서"
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
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 7d2c27ccdba28720596984c46c9d24f9d29c7b15
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2429"></a>컴파일러 오류 C2429
'*언어 기능*'컴파일러 플래그 필요'*컴파일러 옵션*'  
  
언어 기능 지원에 대 한 특정 컴파일러 옵션을 필요합니다.  
  
오류 C2429: 언어 기능에 ' 중첩 된 네임 스페이스-정의 ' 있어야 컴파일러 플래그 ' / std:c + + 최신 '를 정의 하려고 하는 경우에 생성 되는 *복합 네임 스페이스*, Visual Studio 2015 업데이트 3 부터는 하나 이상의 범위 중첩 된 네임 스페이스 이름을 포함 하는 네임 스페이스입니다. 복합 네임 스페이스 정의 C + +&17; 전에 c + +에서 사용할 수 없습니다. 컴파일러 지원 복합 네임 스페이스 정의 때는 [/std:c + + 최신](../../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 지정 합니다.  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
