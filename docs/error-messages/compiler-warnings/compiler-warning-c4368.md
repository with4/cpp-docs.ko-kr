---
title: "컴파일러 경고 C4368 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4368"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4368"
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4368
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member'을\(를\) 관리되는 'type'의 멤버로 정의할 수 없습니다. 혼합 형식은 지원되지 않습니다.  
  
 네이티브 데이터 멤버를 CLR 형식에 포함할 수 없습니다.  
  
 그러나 네이티브 형식에 대한 포인터를 선언하고 관리되는 클래스의 생성자, 소멸자 및 종료자에서 이 포인터의 수명을 제어할 수 있습니다.  자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)를 참조하십시오.  
  
 이 경고는 항상 오류로서 발생합니다.  C4368을 비활성화하려면 [경고](../../preprocessor/warning.md) pragma를 사용하십시오.  
  
## 예제  
 다음 샘플에서는 C4368 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```