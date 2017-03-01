---
title: "컴파일러 오류 C3633 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3633
dev_langs:
- C++
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
caps.latest.revision: 14
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 76b98ae31e8d8416360415fd5989975533d6fb66
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3633"></a>컴파일러 오류 C3633
관리 되는 'type'의 구성원으로 'member'를 정의할 수 없습니다.  
  
CLR 참조 클래스 데이터 멤버는 비-포드 c + + 형식이 될 수 없습니다.  POD 네이티브 형식은 CLR 형식에만 인스턴스화할 수 있습니다.  예를 들어 POD 형식과 복사 생성자 또는 대입 연산자를 포함할 수 없습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3633 오류가 발생 합니다.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  

