---
title: "컴파일러 오류 C2581 | Microsoft Docs"
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
  - "C2581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2581"
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 정적 'operator \=' 함수를 사용할 수 없습니다.  
  
 할당 연산자\(`=`\)가 `static`으로 잘못 선언되었습니다.  할당 연산자는 `static`일 수 없습니다.  자세한 내용은 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2581 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```