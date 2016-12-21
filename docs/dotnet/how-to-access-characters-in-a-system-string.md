---
title: "방법: System::String의 문자에 액세스 | Microsoft Docs"
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
  - "문자[C++], System::String에서 액세스"
  - "예제[C++], 문자열"
  - "문자열[C++], 문자 액세스"
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: System::String의 문자에 액세스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`wchar_t*` 문자열을 사용하는 관리되지 않는 함수에 대한 호출 성능을 향상시키기 위해 <xref:System.String> 개체의 문자에 액세스할 수 있습니다.  이렇게 하면 <xref:System.String> 개체의 첫 번째 문자에 대한 내부 포인터가 생성됩니다.  이 포인터를 직접 조작하거나 이 포인터를 고정하여 일반적인 `wchar_t` 문자열이 필요한 함수에 전달할 수 있습니다.  
  
## 예제  
 `PtrToStringChars`에서는 `byref`라고도 하는 내부 포인터인 <xref:System.Char>를 반환합니다.  따라서 이는 가비지 수집의 영향을 받습니다.  이 포인터를 네이티브 함수에 전달하려는 경우가 아니면 이를 고정할 필요가 없습니다.  
  
 다음과 같은 코드를 생각해 볼 수 있습니다.  `ppchar`는 내부 포인터이므로 고정할 필요가 없습니다. 이 포인터가 가리키는 문자열을 가비지 수집기가 옮기면 `ppchar`도 함께 업데이트됩니다.  [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) 없이도 코드가 작동하며 고정으로 인해 발생할 수 있는 성능 손실도 없습니다.  
  
 네이티브 함수에 `ppchar`를 전달하는 경우 이는 고정 포인터여야 합니다. 가비지 수집기는 관리되지 않는 스택 프레임의 포인터를 업데이트할 수 없습니다.  
  
```  
// PtrToStringChars.cpp  
// compile with: /clr  
#include<vcclr.h>  
using namespace System;  
  
int main() {  
   String ^ mystring = "abcdefg";  
  
   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );  
  
   for ( ; *ppchar != L'\0'; ++ppchar )  
      Console::Write(*ppchar);  
}  
```  
  
  **abcdefg**   
## 예제  
 이 예제에서는 고정이 필요한 부분을 보여 줍니다.  
  
```  
// PtrToStringChars_2.cpp  
// compile with: /clr  
#include <string.h>  
#include <vcclr.h>  
// using namespace System;  
  
size_t getlen(System::String ^ s) {  
   // Since this is an outside string, we want to be secure.  
   // To be secure, we need a maximum size.  
   size_t maxsize = 256;  
   // make sure it doesn't move during the unmanaged call  
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);  
   return wcsnlen(pinchars, maxsize);  
};  
  
int main() {  
   System::Console::WriteLine(getlen("testing"));  
}  
```  
  
 **7**   
## 예제  
 내부 포인터에는 네이티브 C\+\+ 포인터의 모든 속성이 있습니다.  예를 들어, 이 포인터를 사용하여 링크된 데이터 구조를 살펴보고 포인터 하나만으로 삽입과 삭제 작업을 수행할 수 있습니다.  
  
```  
// PtrToStringChars_3.cpp  
// compile with: /clr /LD  
using namespace System;  
ref struct ListNode {  
   Int32 elem;   
   ListNode ^ Next;  
};  
  
void deleteNode( ListNode ^ list, Int32 e ) {   
   interior_ptr<ListNode ^> ptrToNext = &list;  
   while (*ptrToNext != nullptr) {  
      if ( (*ptrToNext) -> elem == e )  
         *ptrToNext = (*ptrToNext) -> Next;   // delete node  
      else  
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node  
   }  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)