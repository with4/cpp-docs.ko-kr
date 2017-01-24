---
title: "방법: C#에서 사용하기 위해 네이티브 클래스 래핑 | Microsoft Docs"
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
  - "클래스[C++], Visual C#"
  - "네이티브 코드[C++], Visual C#"
ms.assetid: 988819ae-cc6a-4453-8ff5-be369210d962
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C#에서 사용하기 위해 네이티브 클래스 래핑
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 샘플에서는 C\#이나 기타 .NET 언어로 작성된 코드에서 사용할 수 있도록 네이티브 C\+\+ 클래스를 래핑하는 방법을 보여 줍니다.  
  
## 예제  
  
```  
// wrap_native_class_for_mgd_consumption.cpp  
// compile with: /clr /LD  
#include <windows.h>  
#include <vcclr.h>  
#using <System.dll>  
  
using namespace System;  
  
class UnmanagedClass {  
public:  
   LPCWSTR GetPropertyA() { return 0; }  
   void MethodB( LPCWSTR ) {}  
};  
  
public ref class ManagedClass {  
public:  
   // Allocate the native object on the C++ Heap via a constructor  
   ManagedClass() : m_Impl( new UnmanagedClass ) {}  
  
   // Deallocate the native object on a destructor  
   ~ManagedClass() {  
      delete m_Impl;  
   }  
  
protected:  
   // Deallocate the native object on the finalizer just in case no destructor is called  
   !ManagedClass() {  
      delete m_Impl;  
   }  
  
public:  
   property String ^  get_PropertyA {  
      String ^ get() {  
         return gcnew String( m_Impl->GetPropertyA());  
      }  
   }  
  
   void MethodB( String ^ theString ) {  
      pin_ptr<const WCHAR> str = PtrToStringChars(theString);  
      m_Impl->MethodB(str);  
   }  
  
private:  
   UnmanagedClass * m_Impl;  
};  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)