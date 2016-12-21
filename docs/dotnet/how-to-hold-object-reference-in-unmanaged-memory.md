---
title: "방법: 관리되지 않는 메모리에 개체 참조 유지 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcroot 키워드[C++], 네이티브 함수에 개체 참조 유지"
  - "개체 참조, 네이티브 함수"
  - "개체[C++], 네이티브 함수에 참조 유지"
  - "참조, 네이티브 함수에 개체 유지"
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 관리되지 않는 메모리에 개체 참조 유지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:System.Runtime.InteropServices.GCHandle>을 래핑하는 gcroot.h를 사용하여 CLR 개체 참조를 관리되지 않는 메모리에 유지할 수 있습니다.  또는 `GCHandle`을 직접 사용할 수 있습니다.  
  
## 예제  
  
```  
// hold_object_reference.cpp  
// compile with: /clr  
#include "gcroot.h"  
using namespace System;  
  
#pragma managed  
class StringWrapper {  
  
private:  
   gcroot<String ^ > x;  
  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      x = str;  
   }  
  
   void PrintString() {  
      String ^ targetStr = x;  
      Console::WriteLine("StringWrapper::x == {0}", targetStr);  
   }  
};  
#pragma unmanaged  
int main() {  
   StringWrapper s;  
   s.PrintString();  
}  
```  
  
  **StringWrapper::x \=\= ManagedString**   
## 예제  
 `GCHandle`을 사용하면 관리되는 개체 참조를 관리되지 않는 메모리에 유지할 수 있습니다.  <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> 메서드를 사용하여 관리되는 개체에 대한 불투명 핸들을 만들고 <xref:System.Runtime.InteropServices.GCHandle.Free%2A>를 사용하여 이를 해제할 수 있습니다.  또한 <xref:System.Runtime.InteropServices.GCHandle.Target%2A> 메서드를 사용하면 관리 코드의 핸들로부터 개체 참조를 다시 얻을 수 있습니다.  
  
```  
// hold_object_reference_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
class StringWrapper {  
   IntPtr m_handle;  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));  
   }  
   ~StringWrapper() {  
      static_cast<GCHandle>(m_handle).Free();  
   }  
  
   void PrintString() {  
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);  
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);  
   }  
};  
  
#pragma unmanaged  
int main() {  
   StringWrapper s;   
   s.PrintString();  
}  
```  
  
  **StringWrapper::m\_handle \=\= ManagedString**   
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)