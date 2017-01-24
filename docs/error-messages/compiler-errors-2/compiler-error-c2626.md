---
title: "컴파일러 오류 C2626 | Microsoft Docs"
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
  - "C2626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2626"
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 익명 구조체 또는 공용 구조체에서는 전용 또는 보호된 데이터 멤버가 허용되지 않습니다.  
  
 익명 구조체 또는 공용 구조체의 멤버는 공용 액세스 권한이 있어야 합니다.  
  
 다음 샘플에서는 C2626을 생성합니다.  
  
```  
// C2626.cpp  
int main() {  
   union {  
   protected:  
      int j;     // C2626, j is protected  
   private:  
      int k;     // C2626, k is private  
   };  
}  
```  
  
 이 문제를 해결하려면 전용 또는 보호된 태그를 제거하세요.  
  
```  
// C2626b.cpp  
int main() {  
   union {  
   public:  
      int i;   // OK, i is public  
   };  
}  
```