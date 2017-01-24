---
title: "컴파일러 오류 C3072 | Microsoft Docs"
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
  - "C3072"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3072"
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3072
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' 연산자는 ref 클래스에 적용할 수 없습니다.  
  
 단항 '`operator`' 연산자를 사용하여 ref 클래스 인스턴스를 핸들 형식으로 변환하십시오.  
  
 CLR 형식에는 네이티브 또는 표준 연산자가 아닌 CLR 연산자가 필요합니다.  자세한 내용은 [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3072 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```