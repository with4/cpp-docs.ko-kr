---
title: "링커 도구 경고 LNK4254 | Microsoft Docs"
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
  - "LNK4254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4254"
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'section1'\(offset\) 섹션이 다른 특성을 사용하여 'section2'\(offset\)에 병합되었습니다.  
  
 한 섹션의 내용을 다른 섹션에 병합했지만 두 섹션의 특성이 서로 다릅니다.  프로그램에서 예기치 않은 결과가 발생할 수도 있습니다.  예를 들어, 읽기 전용으로 설정한 데이터가 쓰기 가능한 섹션에 배치될 수도 있습니다.  
  
 LNK4254를 해결하려면 병합 요청을 수정하거나 제거해야 합니다.  
  
 Visual C\+\+를 사용하여 x86 컴퓨터 및 Windows CE 대상\(ARM, MIPS, SH4 및 Thumb\)을 대상으로 지정하는 경우 .CRT 섹션은 읽기 전용입니다.  코드가 이전 동작\(.CRT 섹션이 읽기\/쓰기 가능\)을 사용하는 경우 예기치 않은 동작이 발생할 수 있습니다.  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [\/MERGE\(섹션 결합\)](../../build/reference/merge-combine-sections.md)  
  
-   [주석](../../preprocessor/comment-c-cpp.md)  
  
## 예제  
 다음 샘플에서는 LNK4254 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```