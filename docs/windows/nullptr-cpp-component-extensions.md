---
title: "nullptr  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__nullptr keyword (C++)"
  - "nullptr keyword [C++]"
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nullptr  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`nullptr` 키워드는 *null 포인터 값*을 나타냅니다.  널 포인터 값을 사용하여 개체 핸들, 내부 포인터 또는 네이티브 포인터가 개체를 가리킵니다.  
  
 관리 코드나 네이티브 코드와 함께  `nullptr`  를 사용합니다.  컴파일러는 적절하게 나타내지만 관리된 혹은 네이티브 null 포인터 값에 대해 다른 지시를 합니다.  이 키워드의 ISO 표준 c \+ \+ 버전을 사용하는 방법에 대한 내용은 [nullptr](../cpp/nullptr.md)를 참조하십시오.  
  
 `__nullptr` 키워드는 `nullptr`과 동일한 의미를 갖는 Microsoft 고유의 키워드입니다.  네이티브 C\/c \+ \+ 코드와  `nullptr` 을  사용하고나서 [\/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션으로 컴파일을 하면 컴파일러는   `nullptr` 이 네이티브 또는 관리 되는 null 포인터 값을 가리키는지 여부를 확인할 수 없습니다.  컴파일러에 명령을 지우려면,  `nullptr` 을 사용하여 관리 되는 값을 지정하거나  `__nullptr` 로 기본 값을 지정합니다.  
  
 `nullptr` 는 Visual Basic `Nothing`와 C\#의 `null`에  keyword키워드에 해당합니다.  
  
## 용도  
 `nullptr` 키워드는 핸들, 네이티브 포인터 또는 함수 인수로 어디든지 사용할 수 있습니다.  
  
 `nullptr`  키워드는 형식이 아니므로 사용할 수 없습니다.  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr`\(하지만  `throw (Object^)nullptr;` 는 작동합니다\)  
  
 `nullptr` 키워드는 다음 포인터 형식 초기화에서 사용할 수 있습니다.  
  
-   네이티브 포인터입니다.  
  
-   Windows 런타임 핸들  
  
-   관리되는 핸들  
  
-   관리되는 내부 포인터  
  
 `nullptr`  키워드는 포인터 또는 핸들 참조가 null 참조를 사용하기 전에 테스트에 사용할 수 있습니다.  
  
 함수는 올바르게 해석하는지 체크하는 오류검사에 대한 null 포인터 값을 사용하는 언어 중에서 호출합니다.  
  
 핸들을 0로 초기화할 수 없습니다. 오직  `nullptr` 만 사용할 수 있습니다.  개체 핸들 상수 0을 할당은 박스형  `Int32` 을 생성하고  `Object^` 으로 변환합니다.  
  
## 예제  
 다음 코드 예제는  `nullptr` 키워드가 핸들을 네이티브 포인터 위치에 관계 없이 사용되거나 함수 인수로 사용할 수 있음을 보여줍니다.  그리고 예제는  `nullptr` 키워드를 사용하여 사용하기 전에 참조를 확인할 수 있음을 보여줍니다.  
  
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
  
## 예제  
 **예제**  
  
 다음 코드 예제에서는  `nullptr`  및 네이티브 포인터에 0을 교대로 사용할 수 있음을 보여줍니다.  
  
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
  
 **Output**  
  
  **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**  
 **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**   
## 예제  
 **예제**  
  
 다음 코드 예제에서는  `nullptr` 가 모든 종류에 대한 핸들 또는 네이티브 포인터 형식으로 해석되는 것을 보여줍니다.  다양한 종류에 대한 핸들을 사용하여 함수 오버 로드를 발생하는 경우 모호성 오류가 생성됩니다.   `nullptr` 은 명시적으로 캐스팅해야 합니다.  
  
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
  
## 예제  
 **예제**  
  
 다음 코드 예제에서는  `nullptr`  캐스팅이 허용되며  `nullptr`  값을 포함하는 캐스트 형식으로 포인터나 핸들을 반환하는 것을 보여줍니다.  
  
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
  
## 예제  
 **예제**  
  
 다음 코드 예제에서는  `nullptr` 가 함수 매개 변수로 사용될 수 있음을 보여줍니다.  
  
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
  
 **Output**  
  
  **테스트**   
## 예제  
 **예제**  
  
 다음 코드 예제에서는 핸들은 선언되고 명시적으로 초기화 하는 경우,  `nullptr` 로 기본적으로 초기화되는 것을 보여줍니다.  
  
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
  
 **Output**  
  
  **NULL**   
## 예제  
 **예제**  
  
 다음 코드 예제에서는  `nullptr` 가  **\/clr** 을 사용하여 컴파일할 때 네이티브 포인터에 할당할 수 있음을 보여줍니다.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## 요구 사항  
 컴파일러 옵션: \(불필요;  **\/ZW**  및  **\/clr**  을 포함한 모든 코드 생성 옵션의 지원\)  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)