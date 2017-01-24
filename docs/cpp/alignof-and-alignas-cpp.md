---
title: "alignof 및 alignas(C++) | Microsoft Docs"
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
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# alignof 및 alignas(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`alignas` 형식 지정자는 변수 및 사용자 정의 형식의 사용자 지정 맞춤을 지정하는 포팅 가능한 C\+\+ 표준 방법입니다.  마찬가지로 `alignof` 연산자도 지정된 형식 또는 변수의 맞춤을 얻는 포팅 가능한 표준 방법입니다.  
  
## 예제  
 클래스, 구조체\/공용 구조체 또는 개별 멤버에 `alignas`를 사용할 수 있습니다.  여러 `alignas` 지정자가 발견되는 경우 컴파일러는 가장 엄격한 지정자\(가장 큰 값을 가진 지정자\)를 선택합니다.  
  
```  
struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  
…  
cout << alignof(Bar) << endl; // output: 16  
  
```  
  
## 참고 항목  
 [맞춤](../cpp/alignment-cpp-declarations.md)