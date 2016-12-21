---
title: "컴파일러 경고 (수준 1) C4829 | Microsoft Docs"
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
  - "C4829"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4829"
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4829
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

main 함수에 대한 매개 변수가 잘못된 것 같습니다.'int main\(Platform::Array\<Platform::String^\>^ argv\)'를 사용하세요.  
  
 main과 같은 특정 함수는 참조 형식 매개 변수를 사용할 수 없습니다.  컴파일은 성공하지만 결과 이미지가 실행되지 않을 수 있습니다.  
  
 다음 샘플에서는 C4829를 생성합니다.  
  
```  
// C4829.cpp  
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp  
int main(Platform::String ^ s) {}   // C4829  
  
```