---
title: "방법: 네이티브 형식으로 핸들 선언 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcroot 키워드[C++]"
  - "핸들, 선언"
  - "형식[C++], 핸들 선언"
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 네이티브 형식으로 핸들 선언
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You cannot declare a handle type in a native type. vcclr.h provides the type\-safe wrapper template `gcroot` to refer to a CLR object from the C\+\+ heap.  이 템플릿을 사용하여 가상 핸들을 네이티브 형식에서 포함시키고 내부 형식인 것으로 취급할 수 있습니다.  대부분의 경우 캐스팅 없이 `gcroot` 개체를 포함된 형식으로 사용할 수 있습니다.  그러나 [for each, in](../dotnet/for-each-in.md)을 사용할 경우 기본 관리되는 참조를 검색하려면 `static_cast`를 사용해야 합니다.  
  
 `gcroot` 템플릿은 가비지 수집되는 힙에 "핸들"을 제공하는 값 클래스인 System::Runtime::InteropServices::GCHandle의 기능을 사용하여 구현됩니다.  핸들 자체는 가비지 수집되지 않으며 더 이상 사용되지 않을 때 `gcroot` 클래스의 소멸자에 의해 해제됩니다. 이 소멸자는 직접 호출할 수 없습니다.  네이티브 힙에 `gcroot` 개체를 인스턴스화하는 경우 해당 리소스에 대해 delete를 호출해야 합니다.  
  
 런타임에서는 핸들과 핸들이 참조하는 CLR 개체 간의 연결을 유지합니다.  CLR 개체가 가비지 수집되는 힙과 함께 이동하면 핸들은 개체의 새 주소를 반환합니다.  변수를 `gcroot` 템플릿에 할당하기 전에 고정할 필요는 없습니다.  
  
## 예제  
 이 샘플에서는 네이티브 스택에 `gcroot` 개체를 만드는 방법을 보여 줍니다.  
  
```  
// mcpp_gcroot.cpp  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
class CppClass {  
public:  
   gcroot<String^> str;   // can use str as if it were String^  
   CppClass() {}  
};  
  
int main() {  
   CppClass c;  
   c.str = gcnew String("hello");  
   Console::WriteLine( c.str );   // no cast required  
}  
```  
  
  **hello**   
## 예제  
 이 샘플에서는 네이티브 힙에 `gcroot` 개체를 만드는 방법을 보여 줍니다.  
  
```  
// mcpp_gcroot_2.cpp  
// compile with: /clr  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
struct CppClass {  
   gcroot<String ^> * str;  
   CppClass() : str(new gcroot<String ^>) {}  
  
   ~CppClass() { delete str; }  
  
};  
  
int main() {  
   CppClass c;  
   *c.str = gcnew String("hello");  
   Console::WriteLine( *c.str );  
}  
```  
  
  **hello**   
## 예제  
 이 샘플에서는 boxed 형식에 `gcroot`를 사용하여 참조 형식이 아닌 값 형식에 대한 참조를 네이티브 형식에 저장하는 `gcroot` 사용법을 보여 줍니다.  
  
```  
// mcpp_gcroot_3.cpp  
// compile with: /clr  
#include < vcclr.h >  
using namespace System;  
  
public value struct V {  
   String^ str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
  **String in V: Hello**   
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)