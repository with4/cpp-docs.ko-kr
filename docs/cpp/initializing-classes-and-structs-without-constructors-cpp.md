---
title: "생성자 없이 클래스 및 구조체 초기화(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 생성자 없이 클래스 및 구조체 초기화(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스, 특히 비교적 간단한 클래스에 대해 항상 생성자를 정의할 필요는 없습니다.  사용자는 다음 예제와 같이 균일 초기화를 사용하여 클래스 또는 구조체의 개체를 초기화할 수 있습니다.  
  
```  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double max;  
    double min;  
};  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    // Member initialization:  
    TempData td { 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default {};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;   
    return 0;  
}  
```  
  
## 참고 항목  
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)   
 [생성자](../cpp/constructors-cpp.md)