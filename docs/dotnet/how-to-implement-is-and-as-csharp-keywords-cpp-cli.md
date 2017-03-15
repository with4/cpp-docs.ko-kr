---
title: "방법: is 및 as C# 키워드 구현(C++/CLI) | Microsoft Docs"
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
  - "as C# 키워드[C++]"
  - "is C# 키워드[C++]"
ms.assetid: bc66c0d1-696b-480d-977c-5d9d1ad1ece6
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: is 및 as C# 키워드 구현(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 `is` 및 `as` C\# 키워드의 기능을 Visual C\+\+에서 구현하는 방법을 보여 줍니다.  
  
 자세한 내용은 [is](../Topic/is%20\(C%23%20Reference\).md) 및 [as](../Topic/as%20\(C%23%20Reference\).md)를 참조하십시오.  
  
## 예제  
  
```  
// CS_is_as.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I {  
public:  
   void F();  
};  
  
ref struct C : public I {  
   virtual void F( void ) { }  
};  
  
template < class T, class U >   
Boolean isinst(U u) {  
   return dynamic_cast< T >(u) != nullptr;  
}  
  
int main() {  
   C ^ c = gcnew C();  
   I ^ i = safe_cast< I ^ >(c);   // is (maps to castclass in IL)  
   I ^ ii = dynamic_cast< I ^ >(c);   // as (maps to isinst in IL)  
  
   // simulate 'as':  
   Object ^ o = "f";  
   if ( isinst< String ^ >(o) )  
      Console::WriteLine("o is a string");  
}  
```  
  
  **o는 문자열**   
## 참고 항목  
 [다른 .NET 언어와의 상호 운용성](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)