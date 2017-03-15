---
title: "컴파일러 오류 C3908 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3908"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3908"
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3908
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

액세스 수준이 'construct'의 수준보다 덜 제한적입니다.  
  
 속성 접근자 메서드\(get 또는 set\)의 액세스 수준은 속성 자체에 지정된 액세스 수준보다 덜 제한적일 수 없습니다.  이벤트 접근자 메서드의 경우에도 마찬가지입니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 및 [event](../../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3908 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```