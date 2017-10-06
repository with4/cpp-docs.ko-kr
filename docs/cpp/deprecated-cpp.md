---
title: "(c + +) 사용 되지 않습니다. | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- deprecated_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9ac25648e2d19da82f6c213992699c237e05c01e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="deprecated-c"></a>사용되지 않음 (C++)
이 항목은 Microsoft 전용에 대 한 declspec 선언 사용 되지 않습니다. C + + 14에 대 한 내용은 `[[deprecated]]` 특성 및 해당 특성 및 Microsoft 전용 declspec 또는 pragma를 사용 하는 경우에 대 한 지침 참조 [c + + 표준 특성](attributes2.md)합니다.

 아래와 같이 예외가 **더 이상 사용 되지** 와 동일한 기능을 제공 하는 선언에서 [더 이상 사용 되지](../preprocessor/deprecated-c-cpp.md) pragma:  
  
-   **사용 되지 않는** 선언을 사용 하면 특정 형태의 함수 오버 로드, 사용 되지 않는 지정 반면에 pragma 형태 모든 오버 로드 된 형태의 함수 이름에 적용 합니다.  
  
-   **사용 되지 않는** 선언 컴파일 타임에 표시 될 메시지를 지정할 수 있습니다. 메시지의 텍스트는 매크로에서 제공될 수 있습니다.  
  
-   매크로와 사용 되지 않는 것에 표시 수는 **더 이상 사용 되지** pragma입니다.  
  
 컴파일러는 사용 되지 않는 식별자 또는 표준의 사용을 발견 하는 경우 [ `[[deprecated]]` ](attributes2.md) 특성에는 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 경고가 throw 됩니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 함수를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 함수가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.  
  
```  
// deprecated.cpp  
// compile with: /W3  
#define MY_TEXT "function is deprecated"  
void func1(void) {}  
__declspec(deprecated) void func1(int) {}  
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}  
__declspec(deprecated(MY_TEXT)) void func3(int) {}  
  
int main() {  
   func1();  
   func1(1);   // C4996  
   func2(1);   // C4996  
   func3(1);   // C4996  
}  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 클래스를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 클래스가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.  
  
```  
// deprecate_class.cpp  
// compile with: /W3  
struct __declspec(deprecated) X {  
   void f(){}  
};  
  
struct __declspec(deprecated("** X2 is deprecated **")) X2 {  
   void f(){}  
};  
  
int main() {  
   X x;   // C4996  
   X2 x2;   // C4996  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)
