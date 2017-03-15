---
title: "컴파일러 오류 C3638 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3638"
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 기본 boxing 및 unboxing 변환 연산자는 다시 정의할 수 없습니다.  
  
 컴파일러는 각 관리되는 클래스에 대해 암시적 boxing을 지원하기 위한 변환 연산자를 정의합니다.  이 연산자는 오버로드할 수 없습니다.  
  
 자세한 내용은 [Implicit Boxing](../../windows/boxing-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3638 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```