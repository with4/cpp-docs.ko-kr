---
title: "첨자 연산자의 해석 | Microsoft Docs"
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
helpviewer_keywords: 
  - "배열[C++], 첨자"
  - "첨자 연산자 해석"
  - "연산자[C++], 첨자 해석"
  - "첨자 연산자, 해석"
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 첨자 연산자의 해석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 연산자와 달리 첨자 연산자\(**\[ \]**\)는 사용자가 다시 정의할 수 있습니다.  첨자 연산자의 기본 동작은 다음 메서드를 사용하여 배열 이름과 첨자를 결합하는 것입니다.  
  
 \*\(\(*array\-name*\) \+ \(*subscript*\)\)  
  
 포인터 형식을 비롯한 모든 추가에서와 마찬가지로 형식 크기를 조정하기 위해 크기 조정이 자동으로 수행됩니다.  따라서 결과 값은 *array\-name*의 원점부터 *subscript*바이트가 아니라 배열의 *subscript*번째 요소입니다. 이 변환에 대한 자세한 내용은 [덧셈 연산자](../cpp/additive-operators-plus-and.md)를 참조하십시오.  
  
 다차원 배열에서도 다음 메서드를 사용하여 주소가 파생됩니다.  
  
 **\(\(**   
 ***array\-name* \) \+ \(**   
 ***subscript* 1**  *max*2 *\* max*3*...max*n\)               **\+** *subscript*2 *\* max*3*...max*n\)                    . . .  *\+* *subscript*n\)\)  
  
## 참고 항목  
 [배열](../cpp/arrays-cpp.md)