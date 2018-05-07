---
title: 'auto_handle:: ~ auto_handle | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_handle.~auto_handle
- msclr.auto_handle.~auto_handle
- auto_handle::~auto_handle
- ~auto_handle
- msclr::auto_handle::~auto_handle
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::~auto_handle
ms.assetid: e83e95a8-015b-4f27-ad63-70efb3690726
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4ba4ab13a2bd4fd16a09f91a5a382401d71ad73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="autohandleautohandle"></a>auto_handle::~auto_handle
`auto_handle` 소멸자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
~auto_handle();  
```  
  
## <a name="remarks"></a>설명  
 소멸자에는 또한 소유한 개체를 destructs 합니다.  
  
## <a name="example"></a>예제  
  
```  
// msl_auto_handle_dtor.cpp  
// compile with: /clr  
#include "msclr\auto_handle.h"  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
public:  
   ClassA() { Console::WriteLine( "ClassA constructor" ); }  
   ~ClassA() { Console::WriteLine( "ClassA destructor" ); }  
};  
  
int main()  
{  
   // create a new scope for a:  
   {  
      auto_handle<ClassA> a = gcnew ClassA;  
   }  
   // a goes out of scope here, invoking its destructor  
   // which in turns destructs the ClassA object.  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor  
ClassA destructor  
done  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\auto_handle.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>참고 항목  
 [auto_handle 멤버](../dotnet/auto-handle-members.md)   
 [auto_handle::release](../dotnet/auto-handle-release.md)   
 [auto_handle::auto_handle](../dotnet/auto-handle-auto-handle.md)