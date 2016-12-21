---
title: "컴파일러 경고 (수준 1) C4965 | Microsoft Docs"
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
  - "C4965"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4965"
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4965
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수 0을 암시적으로 boxing했습니다. nullptr 또는 명시적 캐스팅을 사용하십시오.  
  
 Visual C\+\+에서 값 형식을 암시적으로 boxing합니다.  Managed Extensions for C\+\+를 사용하여 null 할당이라는 결과를 가져오던 명령이 이제는 boxing된 정수에 대한 할당으로 변경되었습니다.  
  
 자세한 내용은 [Boxing](../../windows/boxing-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4965 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4965.cpp  
// compile with: /clr /W1  
int main() {  
   System::Object ^o = 0;   // C4965  
  
   // the previous line is the same as the following line  
   // using Managed Extensions for C++  
   // System::Object *o = __box(0);  
  
   // OK  
   System::Object ^o2 = nullptr;  
   System::Object ^o3 = safe_cast<System::Object^>(0);  
}  
```