---
title: auto_gcroot::reset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::reset
- auto_gcroot::reset
- msclr.auto_gcroot.reset
- auto_gcroot.reset
dev_langs:
- C++
helpviewer_keywords:
- reset method
ms.assetid: dd58467f-3885-4a15-99fb-ed6dd5d19622
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2dc5664ba1313fa09229447c0a86eec2b2b7b31f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="autogcrootreset"></a>auto_gcroot::reset
현재 소유한 개체를 삭제 하 고 필요에 따라 새 개체를 소유한을 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void reset(  
   _element_type _new_ptr = nullptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_new_ptr`  
 (선택 사항) 새 개체입니다.  
  
## <a name="example"></a>예  
  
```  
// msl_auto_gcroot_reset.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
int main()  
{  
   auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );  
   agc1->PrintHello();  
  
   ClassA^ ha = gcnew ClassA( "second" );  
   agc1.reset( ha ); // release first object, reference second  
   agc1->PrintHello();  
  
   agc1.reset(); // release second object, set to nullptr  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor: first  
Hello from first A!  
ClassA constructor: second  
ClassA destructor: first  
Hello from second A!  
ClassA destructor: second  
done  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>참고 항목  
 [auto_gcroot 멤버](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::release](../dotnet/auto-gcroot-release.md)   
 [auto_gcroot::attach](../dotnet/auto-gcroot-attach.md)