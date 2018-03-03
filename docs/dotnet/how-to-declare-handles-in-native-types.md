---
title: "방법: 네이티브 형식으로 핸들 선언 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- gcroot
dev_langs:
- C++
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 097889acd9a77cea5e0a81dd3bd13be712a70550
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-declare-handles-in-native-types"></a>방법: 네이티브 형식으로 핸들 선언
네이티브 형식에 핸들 형식을 선언할 수 없습니다. vcclr.h 형식이 안전한 래퍼 템플릿을 제공 `gcroot` c + + 힙에서 CLR 개체를 참조 하려면. 이 서식 파일을 사용 하 여 네이티브 형식에 가상 핸들을 포함 하 고 기본 형식인 것으로 취급할 수 있습니다. 대부분의 경우에서 사용할 수 있습니다는 `gcroot` 캐스팅 없이 포함 된 형식으로 개체입니다. 그러나 [각 항목에 대해에서](../dotnet/for-each-in.md)를 사용 해야 `static_cast` 를 기본 관리 되는 참조를 검색 합니다.  
  
 `gcroot` 서식 파일은 가비지 수집 힙의 System::Runtime::InteropServices::GCHandle "핸들"를 제공 하는 값 클래스의 기능을 사용 하 여 구현 됩니다. 핸들 자체는 가비지 수집 되지 및 소멸자에 의해 더 이상 사용 중이 경우 해제 되 고 `gcroot` 클래스 (이 소멸자 수동으로 호출할 수 없습니다). 인스턴스화하는 경우는 `gcroot` 호출 해야 개체를 네이티브 힙에 해당 리소스를 삭제 합니다.  
  
 런타임 핸들 및 참조 하는 CLR 개체 간의 연결을 유지 합니다. 가비지 수집 힙을 사용 하 여 CLR 개체를 움직이면 핸들 개체의 새 주소를 반환 합니다. 변수를 할당 하기 전에 고정 될 필요는 없습니다는 `gcroot` 서식 파일입니다.  
  
## <a name="example"></a>예  
 이 샘플을 만드는 방법을 보여 줍니다는 `gcroot` 네이티브 스택에 개체입니다.  
  
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
  
```Output  
hello  
```  
  
## <a name="example"></a>예  
 이 샘플을 만드는 방법을 보여 줍니다는 `gcroot` 네이티브 힙에 있는 개체입니다.  
  
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
  
```Output  
hello  
```  
  
## <a name="example"></a>예  
 이 예제에서는 사용 하는 방법을 보여 줍니다. `gcroot` 참조 형식이 아닌 값 형식에 대 한 참조를 네이티브 형식에서 사용 하 여 유지 하기 위해 `gcroot` boxed 형식에 대해 합니다.  
  
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
  
```Output  
String in V: Hello  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)