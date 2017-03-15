---
title: "컴파일러 경고 (수준 3) C4686 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4686"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4686"
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 3) C4686
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***user\-defined type* ': 동작과 UDT 반환 호출 규칙이 변경되었을 수 있습니다.**  
  
 정의되어 있지 않은 클래스 템플릿 특수화가 반환 형식에 사용되었습니다.  클래스를 인스턴스화하는 방법으로 C4686 경고를 해결할 수 있습니다. 인스턴스를 선언하거나 멤버\(C\<int\>::anything\)에 액세스하여 해결할 수도 있습니다.  
  
 이 경고는 ISO C\+\+ 표준에 맞도록 Visual C\+\+ .NET 2003 컴파일러에 이루어진 변경 사항으로 인해 발생합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 대신 다음 코드를 사용해 보십시오.  
  
```  
// C4686.cpp  
// compile with: /W3  
#pragma warning (default : 4686)  
template <class T>  
class C;  
  
template <class T>  
C<T> f(T);  
  
template <class T>  
class C {};  
  
int main() {  
   f(1);   // C4686  
}  
  
template <class T>  
C<T> f(T) {  
   return C<int>();  
}  
```