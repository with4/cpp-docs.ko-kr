---
title: "컴파일러 경고 (수준 3) C4267 | Microsoft Docs"
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
  - "C4267"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4267"
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4267
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 'size\_t'에서 'type'으로 변환하면서 데이터가 손실될 수 있습니다.  
  
 컴파일러가 `size_t`에서 더 작은 형식으로 변환을 감지했습니다.  
  
 이 경고를 해결하려면 `type` 대신 `size_t`를 사용합니다.  또는 적어도 `size_t`만큼 큰 정수 계열 형식을 사용합니다.  
  
## 예제  
 다음 예제에서는 C4267을 생성합니다.  
  
```  
// C4267.cpp  
// compile by using: cl /W4 C4267.cpp  
void Func1(short) {}  
void Func2(int) {}  
void Func3(long) {}  
void Func4(size_t) {}  
  
int main() {  
   size_t bufferSize = 10;  
   Func1(bufferSize);   // C4267 for all platforms  
   Func2(bufferSize);   // C4267 only for 64-bit platforms  
   Func3(bufferSize);   // C4267 only for 64-bit platforms  
   Func4(bufferSize);   // OK for all platforms  
}  
```