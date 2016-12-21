---
title: "region, endregion | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.endregion"
  - "endregion_CPP"
  - "region_CPP"
  - "vc-pragma.region"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "endregion pragma"
  - "pragma, endregion"
  - "pragma, 지역"
  - "영역 pragma"
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# region, endregion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#pragma region**을 사용하면 Visual Studio 코드 편집기의 [개요 기능](../Topic/Outlining.md)을 사용할 때 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.  
  
## 구문  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### 매개 변수  
 `comment`\(선택적 요소\)  
 코드 편집기에 표시될 주석입니다.  
  
 *name*\(선택적 요소\)  
 영역의 이름입니다.  이 이름은 코드 편집기에 표시됩니다.  
  
## 설명  
 **\#pragma endregion**은 **\#pragma region** 블록의 끝을 표시합니다.  
  
 `#region` 블록은 **\#pragma endregion**으로 종료되어야 합니다.  
  
## 예제  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)