---
title: "컴파일러 경고 C4986 | Microsoft Docs"
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
  - "C4986"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4986"
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4986
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 예외 사양이 이전 선언과 일치 하지 않습니다.  
  
 예외 규정 한 선언 및 다른 많은 경우이 경고를 생성할 수 있습니다.  
  
 C4986는 기본적으로 표시되지 않습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4986 오류가 발생하는 경우를 보여 줍니다.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1()  
{  
    // ...  
}  
  
```  
  
## 예제  
 다음 샘플 코드에서는 이 경고를 제거합니다.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1() throw (X*)  
{  
    // ...  
}  
  
```