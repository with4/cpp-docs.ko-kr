---
title: '방법: lock C# 키워드 구현 (C + + /cli CLI) | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lock statement
- lock C# keyword [C++]
ms.assetid: 436fe544-ffb7-49b9-9798-90794e9974de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dba651a7bcbfb1e8d7a0d107fe2400e222b06111
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127918"
---
# <a name="how-to-implement-the-lock-c-keyword-ccli"></a>방법: lock C# 키워드 구현(C++/CLI)
이 항목에서는 C# 구현 하는 방법을 보여 줍니다. `lock` Visual c + +의 키워드입니다. 
  
 사용할 수도 있습니다는 `lock` c + + 지원 라이브러리에 있는 클래스입니다. 참조 [동기화 (lock 클래스)](../dotnet/synchronization-lock-class.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
  
```  
// CS_lock_in_CPP.cpp  
// compile with: /clr  
using namespace System::Threading;  
ref class Lock {  
   Object^ m_pObject;  
public:  
   Lock( Object ^ pObject ) : m_pObject( pObject ) {  
      Monitor::Enter( m_pObject );  
   }  
   ~Lock() {  
      Monitor::Exit( m_pObject );  
   }  
};  
  
ref struct LockHelper {  
   void DoSomething();  
};  
  
void LockHelper::DoSomething() {  
   // Note: Reference type with stack allocation semantics to provide   
   // deterministic finalization  
  
   Lock lock( this );     
   // LockHelper instance is locked  
}  
  
int main()  
{  
   LockHelper lockHelper;  
   lockHelper.DoSomething();  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [다른 .NET 언어와의 상호 운용성(C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)