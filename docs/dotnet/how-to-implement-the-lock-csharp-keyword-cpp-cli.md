---
title: "방법: lock C# 키워드 구현(C++/CLI) | Microsoft Docs"
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
  - "lock C# 키워드[C++]"
  - "lock 문"
ms.assetid: 436fe544-ffb7-49b9-9798-90794e9974de
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: lock C# 키워드 구현(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 C\# `lock` 키워드를 Visual C\+\+에서 구현하는 방법을 보여 줍니다.  자세한 내용은 [lock 문](../Topic/lock%20Statement%20\(C%23%20Reference\).md)을 참조하십시오.  
  
 C\+\+ 지원 라이브러리에서 `lock` 클래스를 사용할 수도 있습니다.  자세한 내용은 [동기화\(lock 클래스\)](../dotnet/synchronization-lock-class.md)를 참조하십시오.  
  
## 예제  
  
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
  
## 참고 항목  
 [다른 .NET 언어와의 상호 운용성](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)