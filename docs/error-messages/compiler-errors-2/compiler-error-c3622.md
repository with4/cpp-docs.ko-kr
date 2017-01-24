---
title: "컴파일러 오류 C3622 | Microsoft Docs"
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
  - "C3622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3622"
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 'keyword'\(으\)로 선언된 클래스를 인스턴스화할 수 없습니다.  
  
 [abstract](../../windows/abstract-cpp-component-extensions.md) 또는 [\_\_abstract](../../misc/abstract.md)로 표시된 클래스를 인스턴스화하려고 했습니다.  abstract로 표시된 클래스는 기본 클래스일 수 있지만 인스턴스화할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3622 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
  
## 예제  
 다음 샘플에서는 C3622 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3622_b.cpp  
// compile with: /clr:oldSyntax  
__abstract class a {  
};  
int main() {  
   a aa;   // C3622  
}  
```