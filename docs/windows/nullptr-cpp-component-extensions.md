---
title: "nullptr (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be7fcc147a5f6f4b96f7bf7dd68376613489946c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nullptr--c-component-extensions"></a>nullptr(C++ 구성 요소 확장)
`nullptr` 키워드 나타냅니다는 *null 포인터 값*합니다. 개체 핸들, 내부 포인터 또는 원시 포인터 형식 개체를 가리키지 않습니다 나타내기 위해 null 포인터 값을 사용 합니다.  
  
 사용 하 여 `nullptr` 는 관리 코드나 네이티브 코드와 함께 합니다. 컴파일러가 관리 / 네이티브 null 포인터 값에 대 한 적절 한 하지만 서로 다른 지침을 내보냅니다. 이 키워드의 ISO 표준 c + + 버전을 사용 하는 방법에 대 한 정보를 참조 하십시오. [nullptr](../cpp/nullptr.md)합니다.  
  
 `__nullptr` 키워드는 Microsoft 전용 키워드와 같은 의미 있는 `nullptr`, 하지만 네이티브 코드에만 적용 됩니다. 사용 하는 경우 `nullptr` 네이티브 C/c + +로 코드을 다음으로 컴파일하는 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 컴파일러 확인할 수 없습니다 여부 `nullptr` 네이티브 또는 관리 되는 null 포인터 값을 나타냅니다. 컴파일러가 해제 하 여 의도를 사용 하 여 `nullptr` 관리 되는 값을 지정 하려면 또는 `__nullptr` 네이티브 값을 지정 합니다.  
  
 `nullptr` 키워드에 해당 하는 `Nothing` Visual basic에서 및 `null` C#입니다.  
  
## <a name="usage"></a>용도  
 `nullptr` 핸들, 네이티브 포인터 또는 함수 인수로 사용할 수 원격 키워드를 사용할 수 있습니다.  
  
 `nullptr` 키워드 형식이 며 사용 하도록 지원 되지 않습니다.  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr`(하지만 `throw (Object^)nullptr;` 작동)  
  
 `nullptr` 다음 포인터 형식의 초기화에서 키워드를 사용할 수 있습니다.  
  
-   네이티브 포인터입니다.  
  
-   Windows 런타임 핸들  
  
-   관리 되는 핸들  
  
-   관리 되는 내부 포인터  
  
 `nullptr` 포인터 또는 핸들 참조는 참조를 사용 하기 전에 null 여부를 테스트 하는 키워드를 사용할 수 있습니다.  
  
 오류 검사에 대 한 null 포인터 값을 사용 하는 언어 마다 함수 호출이 올바르게 해석 됩니다.  
  
 0;에 대 한 핸들을 초기화할 수 없습니다. 만 `nullptr` 사용할 수 있습니다. 상수 0 개체 핸들을 할당 한 boxed 생성 `Int32` 및 캐스트를 `Object^`합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 것을 보여 줍니다는 `nullptr` 때마다 네이티브 포인터, 핸들에 키워드를 사용할 수 있습니다 또는 함수 인수를 사용할 수 있습니다. 이 예제를 보여 줍니다는 `nullptr` 사용 하기 전에 대 한 참조를 확인 하는 키워드를 사용할 수 있습니다.  
  
```  
// mcpp_nullptr.cpp  
// compile with: /clr  
value class V {};  
ref class G {};  
void f(System::Object ^) {}  
  
int main() {  
// Native pointer.  
   int *pN = nullptr;  
// Managed handle.  
   G ^pG = nullptr;  
   V ^pV1 = nullptr;  
// Managed interior pointer.  
   interior_ptr<V> pV2 = nullptr;  
// Reference checking before using a pointer.  
   if (pN == nullptr) {}  
   if (pG == nullptr) {}  
   if (pV1 == nullptr) {}  
   if (pV2 == nullptr) {}  
// nullptr can be used as a function argument.  
   f(nullptr);   // calls f(System::Object ^)  
}  
```  
  
## <a name="example"></a>예  
 **예제**  
  
 다음 코드 예제에서는 `nullptr` 0 네이티브 포인터에 대 한 서로 바꿔 사용할 수 있습니다.  
  
```  
// mcpp_nullptr_1.cpp  
// compile with: /clr  
class MyClass {  
public:  
   int i;  
};  
  
int main() {  
   MyClass * pMyClass = nullptr;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
  
   pMyClass = 0;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
}  
```  
  
 **출력**  
  
```Output  
pMyClass == nullptr  
  
pMyClass == 0  
  
pMyClass == nullptr  
  
pMyClass == 0  
```  
  
## <a name="example"></a>예  
 **예제**  
  
 다음 코드 예제에서는 `nullptr` 모든 형식에 대 한 핸들 또는 네이티브 포인터 형식으로 해석 됩니다. 다른 형식에 대 한 핸들을 사용한 함수 오버 로드의 경우 모호성 오류가 생성 됩니다. `nullptr` 형식으로 명시적으로 캐스팅 해야 합니다.  
  
```  
// mcpp_nullptr_2.cpp  
// compile with: /clr /LD  
void f(int *){}  
void f(int ^){}  
  
void f_null() {  
   f(nullptr);   // C2668  
   // try one of the following lines instead  
   f((int *) nullptr);  
   f((int ^) nullptr);  
}  
```  
  
## <a name="example"></a>예  
 **예제**  
  
 다음 코드 예제에서는 해당 캐스팅을 보여 줍니다. `nullptr` 수 있으며 포함 된 캐스트 형식에 대 한 포인터 또는 핸들 반환는 `nullptr` 값입니다.  
  
```  
// mcpp_nullptr_3.cpp  
// compile with: /clr /LD  
using namespace System;  
template <typename T>   
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type  
  
int main() {  
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)  
  
   // Delete the following line to resolve.  
   f(nullptr);  
  
   f(0);   // T = int, call f(int)  
}  
```  
  
## <a name="example"></a>예  
 **예제**  
  
 다음 코드 예제에서는 `nullptr` 함수 매개 변수로 사용할 수 있습니다.  
  
```  
// mcpp_nullptr_4.cpp  
// compile with: /clr  
using namespace System;  
void f(Object ^ x) {  
   Console::WriteLine("test");  
}  
  
int main() {  
   f(nullptr);  
}  
```  
  
 **출력**  
  
```Output  
test  
```  
  
## <a name="example"></a>예  
 **예제**  
  
 다음 코드 예제에서는 핸들은 선언 되 고 명시적으로 초기화 하는 경우는 기본적으로 초기화를 보여 줍니다. `nullptr`합니다.  
  
```  
// mcpp_nullptr_5.cpp  
// compile with: /clr  
using namespace System;  
ref class MyClass {  
public:  
   void Test() {  
      MyClass ^pMyClass;   // gc type  
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");  
   }  
};  
  
int main() {  
   MyClass ^ x = gcnew MyClass();  
   x -> Test();  
}  
```  
  
 **출력**  
  
```Output  
NULL  
```  
  
## <a name="example"></a>예  
 **예제**  
  
 다음 코드 예제에서는 `nullptr` 사용 하 여 컴파일하면 네이티브 포인터에 할당할 수 **/clr**합니다.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 컴파일러 옵션: (하지 필요 합니다; 모든 코드 생성 옵션을 포함 하 여에서 지 원하는 **/ZW** 및 **/clr**)  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼의 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)