---
title: "컴파일러 오류 C2951 | Microsoft Docs"
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
  - "C2951"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2951"
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2951
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 선언은 전역, 네임스페이스 또는 클래스 범위에서만 허용됩니다.  
  
 전역 또는 네임스페이스 범위 외부에서는 제네릭 또는 템플릿 클래스를 선언할 수 없습니다.  제네릭 또는 템플릿을 포함 파일에서 선언하는 경우에는 포함 파일이 전역 범위에 있어야 합니다.  
  
 다음 샘플에서는 C2951 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 제네릭을 사용하는 경우에도 C2951이 발생할 수 있습니다.  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```