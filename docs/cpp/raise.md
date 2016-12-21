---
title: "__raise | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__raise"
  - "__raise_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__raise 키워드[C++]"
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __raise
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트의 호출 사이트를 강조합니다.  
  
## 구문  
  
```  
  
__raise   
method-declarator  
;  
  
```  
  
## 설명  
 관리 코드에서 이벤트가 정의된 클래스 내에서만 이벤트를 발생시킬 수 있습니다.  자세한 내용은 [event](../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 비이벤트를 호출할 경우 `__raise` 키워드를 사용하면 오류가 생략됩니다.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## 예제  
  
```  
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [이벤트 처리](../cpp/event-handling.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)