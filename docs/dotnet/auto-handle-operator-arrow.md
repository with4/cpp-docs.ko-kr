---
title: auto_handle::operator-&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_handle::operator->
- auto_handle.operator->
- auto_handle::operator->
- msclr.auto_handle.operator->
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::operator->
ms.assetid: c8c7a771-ea15-41fa-981a-065b8d1162b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1c3e8fe0c1ecd30ff92aae5540fa4bda4268e4a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104895"
---
# <a name="autohandleoperator-gt"></a>auto_handle::operator-&gt;
멤버 액세스 연산자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
_element_type ^ operator->();  
```  
  
## <a name="return-value"></a>반환 값  
 개체에서 래핑된 `auto_handle`합니다.  
  
## <a name="example"></a>예제  
  
```  
// msl_auto_handle_op_arrow.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
  
   int m_i;  
};  
  
int main() {  
   auto_handle<ClassA> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
  
   a->m_i = 5;  
   Console::WriteLine( "a->m_i = {0}", a->m_i );  
}  
```  
  
```Output  
Hello from first A!  
a->m_i = 5  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\auto_handle.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>참고 항목  
 [auto_handle 멤버](../dotnet/auto-handle-members.md)   
 [auto_handle::get](../dotnet/auto-handle-get.md)